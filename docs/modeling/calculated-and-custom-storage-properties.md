---
title: "계산 및 사용자 지정 저장소 속성 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Domain-Specific Language, programming domain properties
ms.assetid: 42b785f9-2b0f-4f13-a6b4-246e5e0d477a
caps.latest.revision: "19"
author: alancameronwills
ms.author: awills
manager: douge
ms.workload: multiple
ms.openlocfilehash: cf841cf70f092fb38adc42bfa6271c6c3aa121d1
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="calculated-and-custom-storage-properties"></a>계산된 저장소 속성 및 사용자 지정 저장소 속성
도메인 특정 언어 (DSL)의 모든 도메인 속성 언어 탐색기에서 다이어그램에 사용자에 게 표시할 수 있습니다 및 프로그램 코드에서 액세스할 수 있습니다. 그러나 속성은 해당 값을 저장 하는 방식에서 다릅니다.  
  
## <a name="kinds-of-domain-properties"></a>도메인 속성의 종류  
 DSL 정의에서 설정할 수 있습니다는 **종류** 도메인 속성에는 다음 표에 나열 된의:  
  
|도메인 속성 종류|설명|  
|--------------------------|-----------------|  
|**표준** (기본값)|저장 되는 도메인 속성은 *저장* 및 파일에 직렬화 합니다.|  
|**계산**|읽기 전용 도메인 속성 저장소에 저장 되지 않지만 다른 값에서 계산입니다.<br /><br /> 예를 들어 `Person.Age` 에서 계산 될 수 `Person.BirthDate`합니다.<br /><br /> 계산을 수행 하는 코드를 제공 해야 합니다. 일반적으로 다른 도메인 속성에서 값을 계산할 수 있습니다. 그러나 외부 리소스를 사용할 수 있습니다.|  
|**사용자 지정 저장소**|도메인 속성 저장소에 직접 저장 되지 않지만 get 및 set을 둘 다 수입니다.<br /><br /> 가져오기 및 값을 설정 하는 메서드를 제공 해야 합니다.<br /><br /> 예를 들어 `Person.FullAddress` 에 저장할 수 `Person.StreetAddress`, `Person.City`, 및 `Person.PostalCode`합니다.<br /><br /> 또한 가져오고 데이터베이스에서 값을 설정 하는 예제에 대 한 외부 리소스에 액세스할 수 있습니다.<br /><br /> 코드는 저장소에 값을 설정 하지 않아야 때 `Store.InUndoRedoOrRollback` 그렇습니다. 참조 [트랜잭션 및 사용자 지정 Setter](#setters)합니다.|  
  
## <a name="providing-the-code-for-a-calculated-or-custom-storage-property"></a>계산 또는 사용자 지정 저장소 속성에 대 한 코드를 제공합니다.  
 계산 또는 사용자 지정 저장소로 도메인 속성의 종류를 설정 하는 경우 액세스 방법을 제공 해야 합니다. 솔루션을 빌드할 때 오류 보고서를 알려는 데 필요한 사항입니다.  
  
#### <a name="to-define-a-calculated-or-custom-storage-property"></a>Calculated 또는 사용자 지정 저장소 속성을 정의 하려면  
  
1.  DslDefinition.dsl, 다이어그램 또는 도메인 속성 선택 **DSL 탐색기**합니다.  
  
2.  에 **속성** 창의 설정는 **종류** 필드를 **계산** 또는 **사용자 지정 저장소**합니다.  
  
     또한 설정 되어 있어야 해당 **형식** 말하고 합니다.  
  
3.  클릭 **모든 템플릿 변형** 의 도구 모음에서 **솔루션 탐색기**합니다.  
  
4.  **빌드** 메뉴에서 **솔루션 빌드**를 클릭합니다.  
  
     다음과 같은 오류 메시지가: "*YourClass* Get에 대 한 정의 포함 하지 않는*YourProperty*."  
  
5.  오류 메시지를 두 번 클릭 합니다.  
  
     Dsl\GeneratedCode\DomainClasses.cs 또는 DomainRelationships.cs 열립니다. 강조 표시 된 메서드 호출 위에 주석 하 라는 메시지가 표시에 대 한 Get 구현을 제공*YourProperty*().  
  
    > [!NOTE]
    >  이 파일은 DslDefinition.dsl에서 생성 됩니다. 이 파일을 편집 하는 경우 변경 내용이 손실 됩니다 클릭 하면 다음에 **모든 템플릿 변형**합니다. 대신 별도 파일에 필요한 메서드를 추가 합니다.  
  
6.  예를 들어 CustomCode 별도 폴더에 클래스 파일을 열거나 만듭니다\\*YourDomainClass*. cs 합니다.  
  
     네임 스페이스는 생성된 된 코드에서 동일 해야 합니다.  
  
7.  클래스 파일을 부분적으로 구현 된 도메인 클래스를 작성 합니다. 클래스에서 누락 된에 대 한 정의 작성 `Get` 메서드를 다음 예제와 유사 합니다.  
  
    ```  
    namespace Company.FamilyTree  
    {  public partial class Person  
       {  int GetAgeValue()  
          { return System.DateTime.Today.Year - this.BirthYear; }  
    }  }  
    ```  
  
8.  설정한 경우 **종류** 를 **사용자 지정 저장소**를 제공 해야 합니다는 `Set` 메서드. 예:  
  
    ```  
    void SetAgeValue(int value)  
    { if (!Store.InUndoRedoOrRollback)  
        this.BirthYear =   
            System.DateTime.Today.Year - value; }  
    ```  
  
     코드는 저장소에 값을 설정 하지 않아야 때 `Store.InUndoRedoOrRollback` 그렇습니다. 참조 [트랜잭션 및 사용자 지정 Setter](#setters)합니다.  
  
9. 솔루션을 빌드하고 실행합니다.  
  
10. 속성을 테스트 합니다. 시도 하면 확인 **실행 취소** 및 **다시 실행**합니다.  
  
##  <a name="setters"></a>트랜잭션 및 Setter를 사용자 지정  
 사용자 지정 저장소 속성의 Set 메서드의 않아도, 트랜잭션을 열지 활성화 된 트랜잭션 내부 메서드는 일반적으로 하기 때문에 합니다.  
  
 그러나 실행 취소 또는 다시 실행 하면 사용자가 또는 트랜잭션이 롤백되는 경우이 집합 메서드를 호출도 수 있습니다. 때 <xref:Microsoft.VisualStudio.Modeling.Store.InUndoRedoOrRollback%2A> 가 true 이면 Set 메서드가 다음과 같이 동작 합니다.  
  
-   다른 도메인 속성에 값을 지정 하는 같은 저장소에 변경 하면 안 합니다. 실행 취소 관리자는 해당 값을 설정 합니다.  
  
-   그러나 해당 데이터베이스 또는 파일 내용을 스토어 외부 개체 등의 외부 리소스를 업데이트 해야 합니다. 저장소에 값을 가진 synchronism에 유지 됩니다는 있는지 확인 합니다.  
  
 예:  
  
```  
void SetAgeValue(int value)  
{   
  // If we are in Undo, no changes to Store objects:  
  if (!this.Store.InUndoRedoOrRollback)  
  {   
    this.BirthYear = System.DateTime.Today.Year - value;   
  }  
  // But always update external objects:  
  System.IO.File.WriteAllText(AgeFile, value);  
}  
```  
  
 트랜잭션에 대 한 자세한 내용은 참조 하십시오. [탐색 및 프로그램 코드에서 모델 업데이트](../modeling/navigating-and-updating-a-model-in-program-code.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [탐색 및 프로그램 코드에서 모델 업데이트](../modeling/navigating-and-updating-a-model-in-program-code.md)   
 [도메인 속성의 속성](../modeling/properties-of-domain-properties.md)   
 [도메인별 언어 정의 방법](../modeling/how-to-define-a-domain-specific-language.md)