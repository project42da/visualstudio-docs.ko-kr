---
title: "도메인별 언어에서 코드 생성 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e3706cc9-2afd-456a-a879-68425a248ebc
caps.latest.revision: 13
author: "alancameronwills"
ms.author: "awills"
manager: "douge"
caps.handback.revision: 13
---
# 도메인별 언어에서 코드 생성
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Microsoft [!INCLUDE[dsl](../modeling/includes/dsl_md.md)]코딩하다, 문서,구성파일 및 기타 항목을 모델에 표현 되는 데이터를 생성 하는 강력한 방법을 제공 합니다.  사용 하 여 [!INCLUDE[dsl](../modeling/includes/dsl_md.md)], 데이터를 나타내는 클래스만들다수 있습니다 및 클래스의 이름을 가진 텍스트 서식 파일을 작성할 수 있습니다 및 속성 데이터를 반영 합니다.  
  
 예를 들어 Fabrikam의XML파일을고객의 이름과전자 메일주소가 있습니다.  모델은 고객에 포함 하는클래스, 속성 이름 및전자 메일의 개발자가만들다합니다.  이러한프로세스에 모든 고객은HTML페이지의 일부분으로 만드는이 부분을 포함 하 여 데이터를 여러 가지 텍스트 서식 파일 쓰기:  
  
```  
<table>  
<# foreach (Customer c in ContactList) {  #>  
  <tr><td> <#= c.FullName #> </td>   
      <td> <#= c.EmailAddress #> </td> </tr>  
<# } #>  </table>  
```  
  
 고객데이터베이스를 처리할 때 모델 저장소로XML파일 읽기입니다.   A  *지시문 프로세서*를 사용 하 여 만든, [!INCLUDE[dsl](../modeling/includes/dsl_md.md)],템플릿텍스트 고객클래스를코딩하다에 사용할 수 있습니다. 다양 한 텍스트 서식 파일과 같은 저장소에 대해 실행할 수 있습니다.  
  
 텍스트 서식 파일에 필수입니다 [!INCLUDE[dsl](../modeling/includes/dsl_md.md)].  도메인 모델도 있는 VSPackage 및 도구를 통합 하는 데 사용 되는 컨트롤의 요소에 대 한소스코딩하다를 생성 하는 데 사용 됩니다 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
 이 섹션을만들다방법을 설명 합니다, 수정 및디버그하다텍스트 서식 파일에 사용 되는 [!INCLUDE[dsl](../modeling/includes/dsl_md.md)].  
  
## 단원 내용  
 [텍스트 템플릿에서 모델에 액세스](../modeling/accessing-models-from-text-templates.md)  
  
 DSL\(Domain\-Specific Language\)텍스트 서식 파일에서 참조 하는 방법에 대 한 기본 정보를 제공 합니다.  
  
 [연습: 모델에 액세스하는 텍스트 템플릿 디버깅](../Topic/Walkthrough:%20Debugging%20a%20Text%20Template%20that%20Accesses%20a%20Model.md)  
  
 DSL\(Domain\-Specific Language\)에 참조 텍스트템플릿을디버깅및 문제 해결 작업을 수행 하는 방법에 설명 합니다.  
  
 [연습: 생성된 지시문 프로세서에 호스트 연결](../modeling/walkthrough-connecting-a-host-to-a-generated-directive-processor.md)  
  
 설명 사용자 지정호스트생성 된 지시문 프로세서에연결하다하는 방법입니다.  
  
 [DslTextTransform 명령](../modeling/the-dsltexttransform-command.md)  
  
 명령줄이 언어 참조 텍스트 서식 파일의 해당 TextTransform실행 파일실행 명령 파일에 설명 합니다.  
  
## 참조  
 [T4 텍스트 템플릿 쓰기](../modeling/writing-a-t4-text-template.md)  
  
 텍스트 템플릿 지시문과 제어 블록의 구문을 제공합니다.  
  
## 관련 단원  
 [T4 텍스트 템플릿을 사용하여 디자인 타임 코드 생성](../modeling/design-time-code-generation-by-using-t4-text-templates.md)  
  
 텍스트템플릿변환프로세스에 대해 설명 합니다.  
  
 [빌드 프로세스의 코드 생성](../modeling/code-generation-in-a-build-process.md)  
  
 DSL을빌드서버에서 파일을 생성 하는 경우이 항목을 참조 합니다.