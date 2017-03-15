---
title: "Managed Extensibility Framework 편집기에서 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- editors [Visual Studio SDK], new - using MEF for extensions
ms.assetid: 3f59a285-6c33-4ae3-a4fb-ec1f5aa21bd1
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 5658ecf52637a38bc3c2a5ad9e85b2edebf7d445
ms.openlocfilehash: 6a5cb0ae0f8da6af939588ad358e6b5b1b3b108e
ms.lasthandoff: 02/22/2017

---
# <a name="managed-extensibility-framework-in-the-editor"></a>편집기에서 관리 되는 확장성 프레임 워크
편집기는 프레임 워크 MEF (Managed Extensibility) 구성 요소를 사용 하 여 빌드됩니다. 사용자 고유의 MEF 구성 요소 편집기를 확장 하 작성할 수 있으며, 코드 편집기 구성 요소에도 사용할 수 있습니다.  
  
## <a name="overview-of-the-managed-extensibility-framework"></a>관리 되는 확장성 프레임 워크 개요  
 MEF에 추가 하 고 응용 프로그램 또는 MEF 프로그래밍 모델을 따르며 구성의 기능을 수정할 수 있게 해 주는.NET 라이브러리입니다. Visual Studio 편집기 모두 제공 하 고 수 MEF 구성 요소를 사용 합니다.  
  
 MEF는.NET Framework 버전 4 System.ComponentModel.Composition.dll 어셈블리에 포함 되어 있습니다.  
  
 MEF에 대 한 자세한 내용은 참조 [Framework MEF (Managed Extensibility)](http://msdn.microsoft.com/Library/6c61b4ec-c6df-4651-80f1-4854f8b14dde)합니다.  
  
### <a name="component-parts-and-composition-containers"></a>구성 요소 파트와 컴퍼지션 컨테이너  
 구성 요소 부분은 다음 중 하나 (또는 둘 다)을 수행할 수 있는 클래스의 멤버 이거나 클래스:  
  
-   다른 구성 요소를 사용 합니다.  
  
-   다른 구성 요소에서 사용할 수  
  
 예를 들어 쇼핑 응용 프로그램을 웨어하우스 인벤토리 구성 요소에서 제공 하는 제품 가용성 데이터에 의존 하는 주문 항목 구성 요소가 있는 것이 좋습니다. MEF 관점에서 인벤토리 파트 수 *내보내기* 제품 가용성 데이터와 주문 항목 파트 수 *가져올* 데이터입니다. 주문 입력 부분와 인벤토리 파트; 서로 대 한 알 수 없는 *컴퍼지션 컨테이너* (호스트 응용 프로그램에서 제공)는 내보내기, 집합을 유지 하 고 내보내기를 해결 하는 일을 담당 하 고 가져옵니다.  
  
 컴퍼지션 컨테이너 <xref:System.ComponentModel.Composition.Hosting.CompositionContainer>, 일반적으로 호스트에 의해 소유.</xref:System.ComponentModel.Composition.Hosting.CompositionContainer> 컴퍼지션 컨테이너를 유지 관리는 *카탈로그* 내보낸된 구성 요소입니다.  
  
### <a name="exporting-and-importing-component-parts"></a>구성 요소 파트 내보내기 및 가져오기  
 공용 클래스 또는 클래스 (속성 또는 메서드)의 공용 멤버 함수로 구현으로 모든 기능을 내보낼 수 있습니다. <xref:System.ComponentModel.Composition.Primitives.ComposablePart>.</xref:System.ComponentModel.Composition.Primitives.ComposablePart> 구성 요소 부분을 파생 시킬 필요가 없습니다. 대신, 추가 해야는 <xref:System.ComponentModel.Composition.ExportAttribute>특성을 클래스 또는 클래스 멤버에 내보낼.</xref:System.ComponentModel.Composition.ExportAttribute> 이 특성은 지정 된 *계약* 파트는 다른 구성 요소에서 기능을 가져올 수 있습니다.  
  
### <a name="the-export-contract"></a>내보내기 계약  
 <xref:System.ComponentModel.Composition.ExportAttribute>(클래스, 인터페이스 또는 구조체)는 내보낼 엔터티를 정의 합니다.</xref:System.ComponentModel.Composition.ExportAttribute> 일반적으로 export 특성 내보내기의 형식을 지정 하는 매개 변수를 사용 합니다.  
  
```  
[Export(typeof(ContentTypeDefinition))]  
class TestContentTypeDefinition : ContentTypeDefinition {   }  
```  
  
 기본적으로 <xref:System.ComponentModel.Composition.ExportAttribute>형식을 내보낼 클래스는 계약을 정의 하는 특성</xref:System.ComponentModel.Composition.ExportAttribute>  
  
```  
[Export]  
[Name("Structure")]  
[Order(After = "Selection", Before = "Text")]  
class TestAdornmentLayerDefinition : AdornmentLayerDefinition {   }  
```  
  
 예제에서는 기본 `[Export]` 특성은 `[Export(typeof(TestAdornmentLayerDefinition))]`합니다.  
  
 다음 예제와 같이 속성 또는 메서드를 내보낼 수도 있습니다.  
  
```  
[Export]  
[Name("Scarlet")]  
[Order(After = "Selection", Before = "Text")]  
public AdornmentLayerDefinition scarletLayerDefinition;  
```  
  
### <a name="importing-a-mef-export"></a>MEF 내보내기와 가져오기  
 계약 (일반적으로 형식)는 것을 내보낸 하 고 추가 알고 있어야 MEF 내보내기에 사용 하려는 경우는 <xref:System.ComponentModel.Composition.ImportAttribute>특성 값이.</xref:System.ComponentModel.Composition.ImportAttribute> 기본적으로 가져오기 특성에는 하나의 매개 변수를 수정 하는 클래스의 형식입니다. 다음 줄의 코드 가져오기는 <xref:Microsoft.VisualStudio.Text.Classification.IClassificationTypeRegistryService>유형.</xref:Microsoft.VisualStudio.Text.Classification.IClassificationTypeRegistryService>  
  
```  
[Import]  
internal IClassificationTypeRegistryService ClassificationRegistry;  
```  
  
## <a name="getting-editor-functionality-from-a-mef-component-part"></a>MEF 구성 요소 부분에서 편집기 기능 가져오기  
 기존 코드 MEF 구성 요소 일부인 경우 편집기 구성 요소를 사용 하 여 MEF 메타 데이터를 사용할 수 있습니다.  
  
#### <a name="to-consume-editor-functionality-from-a-mef-component-part"></a>MEF 구성 요소 부분에서 편집기 기능을 사용 하려면  
  
1.  전역 어셈블리 캐시 (GAC)에 있는 System.Composition.ComponentModel.dll 하 고 편집기 어셈블리에 대 한 참조를 추가 합니다.  
  
2.  추가 관련 문을 사용 합니다.  
  
    ```  
    using System.ComponentModel.Composition;  
    using Microsoft.VisualStudio.Text;  
    ```  
  
3.  추가 된 `[Import]` 을 서비스 인터페이스, 특성을 다음과 같이 합니다.  
  
    ```  
    [Import]  
    ITextBufferFactoryService textBufferService;  
    ```  
  
4.  서비스를 가져온 경우에 해당 구성 요소 중 하나를 사용할 수 있습니다.  
  
5.  에 어셈블리를 컴파일한 경우는... Visual Studio 설치의 \Common7\IDE\Components\ 폴더입니다.  
  
## <a name="see-also"></a>참고 항목  
 [언어 서비스 및 편집기 확장 지점](../extensibility/language-service-and-editor-extension-points.md)
