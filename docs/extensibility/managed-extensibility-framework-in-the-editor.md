---
title: "편집기에서 Extensibility Framework 관리 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editors [Visual Studio SDK], new - using MEF for extensions
ms.assetid: 3f59a285-6c33-4ae3-a4fb-ec1f5aa21bd1
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 4677b10d54a6c591c2f60e4c0b1f2978ad49a0ca
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="managed-extensibility-framework-in-the-editor"></a>편집기에서 관리 되는 확장 프레임 워크
편집기는 프레임 워크 MEF (Managed Extensibility) 구성 요소를 사용 하 여 작성 됩니다. 사용자 자신의 MEF 구성 요소 편집기를 확장 하 작성할 수 있으며, 코드 편집기 구성 요소에도 사용할 수 있습니다.  
  
## <a name="overview-of-the-managed-extensibility-framework"></a>Managed Extensibility Framework 개요  
 MEF는 응용 프로그램 또는 구성 요소 뒤에 오는 MEF 프로그래밍 모델의 기능을 수정 하 고 추가할 수 있는.NET 라이브러리입니다. Visual Studio 편집기 제공할 수도 있고 MEF 구성 요소 부분을 사용 합니다.  
  
 MEF는.NET Framework 버전 4 System.ComponentModel.Composition.dll 어셈블리에 포함 되어 있습니다.  
  
 MEF에 대 한 자세한 내용은 참조 [Framework MEF (Managed Extensibility)](/dotnet/framework/mef/index)합니다.  
  
### <a name="component-parts-and-composition-containers"></a>구성 요소와 컴퍼지션 컨테이너  
 구성 요소 부분은 클래스 또는 다음 중 하나 (또는 둘 다) 할 수 있는 클래스의 멤버입니다.  
  
-   다른 구성 요소 사용  
  
-   다른 구성 요소에서 사용할 수  
  
 예를 들어 쇼핑 응용 프로그램을 웨어하우스 인벤토리 구성 요소에서 제공 하는 가용성 데이터 제품에 따라 달라 지는 주문 입력 구성 요소에 있는 것이 좋습니다. MEF 측면에서 인벤토리 파트 수 *내보내기* 제품 가용성 데이터와 주문 항목 파트 수 *가져올* 데이터입니다. 주문 입력 부분, 인벤토리 부분 필요가 없습니다; 서로 대해 알고 *컴퍼지션 컨테이너* (호스트 응용 프로그램에서 제공) 및 exports를 해결 하는 내보내기, 집합을 유지 관리를 담당 하 고 가져옵니다.  
  
 컴퍼지션 컨테이너 <xref:System.ComponentModel.Composition.Hosting.CompositionContainer>, 일반적으로 호스트에서 소유 하 고 있습니다. 컴퍼지션 컨테이너를 유지 관리는 *카탈로그* 내보낸된 구성 요소입니다.  
  
### <a name="exporting-and-importing-component-parts"></a>구성 요소 파트 내보내기 및 가져오기  
 공용 클래스 또는 클래스 (속성 또는 메서드)의 공용 멤버 함수로 구현으로 모든 기능을 내보낼 수 있습니다. 사용자 구성 요소 부분에서 파생 될 필요가 없습니다 <xref:System.ComponentModel.Composition.Primitives.ComposablePart>합니다. 대신 추가 해야 합니다는 <xref:System.ComponentModel.Composition.ExportAttribute> 클래스 또는 클래스 멤버를 내보낼에 특성입니다. 이 특성은 지정 된 *계약* 파트는 다른 구성 요소에서 기능을 통해 기능을 가져올 수 있습니다.  
  
### <a name="the-export-contract"></a>내보내기 계약  
 <xref:System.ComponentModel.Composition.ExportAttribute> 내보낸 (클래스, 인터페이스 또는 구조체) 엔터티를 정의 합니다. 일반적으로 내보내기 특성은 내보내기의 유형을 지정 하는 매개 변수를 사용 합니다.  
  
```  
[Export(typeof(ContentTypeDefinition))]  
class TestContentTypeDefinition : ContentTypeDefinition {   }  
```  
  
 기본적으로는 <xref:System.ComponentModel.Composition.ExportAttribute> 특성의 내보내기 클래스 형식인 있는 계약을 정의 합니다.  
  
```  
[Export]  
[Name("Structure")]  
[Order(After = "Selection", Before = "Text")]  
class TestAdornmentLayerDefinition : AdornmentLayerDefinition {   }  
```  
  
 예제에서는 기본 `[Export]` 특성은 같습니다 `[Export(typeof(TestAdornmentLayerDefinition))]`합니다.  
  
 다음 예제와 같이 속성 또는 메서드를 내보낼 수도 있습니다.  
  
```  
[Export]  
[Name("Scarlet")]  
[Order(After = "Selection", Before = "Text")]  
public AdornmentLayerDefinition scarletLayerDefinition;  
```  
  
### <a name="importing-a-mef-export"></a>MEF 내보내기 가져오기  
 계약 (일반적으로 형식) 있는 것을 내보낸 더하고 알고 있어야 MEF 내보내기를 사용 하려는 경우는 <xref:System.ComponentModel.Composition.ImportAttribute> 해당 값이 있는 특성입니다. 기본적으로 import 특성 수정 하는 클래스의 형식을 나타내는 하나의 매개 변수를 사용 합니다. 다음 줄의 코드 가져오기는 <xref:Microsoft.VisualStudio.Text.Classification.IClassificationTypeRegistryService> 유형입니다.  
  
```  
[Import]  
internal IClassificationTypeRegistryService ClassificationRegistry;  
```  
  
## <a name="getting-editor-functionality-from-a-mef-component-part"></a>MEF 구성 요소 부분에서 편집기 기능 가져오기  
 기존 코드 MEF 구성 요소 일부인 경우 편집기 구성 요소 부분을 사용 하 여 MEF 메타 데이터를 사용할 수 있습니다.  
  
#### <a name="to-consume-editor-functionality-from-a-mef-component-part"></a>MEF 구성 요소 부분에서 편집기 기능을 사용 하려면  
  
1.  전역 어셈블리 캐시 (GAC)에 있는 System.Composition.ComponentModel.dll 하 고 편집기 어셈블리에 대 한 참조를 추가 합니다.  
  
2.  추가 관련 문을 사용 하 여 합니다.  
  
    ```  
    using System.ComponentModel.Composition;  
    using Microsoft.VisualStudio.Text;  
    ```  
  
3.  추가 `[Import]` 서비스 인터페이스에 특성을 다음과 같이 합니다.  
  
    ```  
    [Import]  
    ITextBufferFactoryService textBufferService;  
    ```  
  
4.  서비스를 가져온 경우 해당 구성 요소 중 하나를 사용할 수 있습니다.  
  
5.  에 배치 하 여 어셈블리 컴파일한 경우는... Visual Studio 설치의 \Common7\IDE\Components\ 폴더입니다.  
  
## <a name="see-also"></a>참고 항목  
 [언어 서비스 및 편집기 확장 지점](../extensibility/language-service-and-editor-extension-points.md)