---
title: "프로그램 코드에서 레이어 모델 탐색 및 업데이트 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- layer models, navigating in program code
- layer models, updating in program code
ms.assetid: c60edc87-33ee-4964-a954-40069f9febf3
caps.latest.revision: "20"
author: alexhomer1
ms.author: ahomer
manager: douge
ms.openlocfilehash: 50da0b90dd1c8924d8772eabd83265ff3827c2c2
ms.sourcegitcommit: ec1c7e7e3349d2f3a4dc027e7cfca840c029367d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2017
---
# <a name="navigate-and-update-layer-models-in-program-code"></a>프로그램 코드에서 레이어 모델 탐색 및 업데이트
이 항목에서는 프로그램 코드를 사용하여 탐색하고 업데이트할 수 있는 레이어 모델의 요소와 관계에 대해 설명합니다. 사용자의 관점에서 종속성 다이어그램에 대 한 자세한 내용은 참조 [종속성 다이어그램: 참조](../modeling/layer-diagrams-reference.md) 및 [종속성 다이어그램: 지침](../modeling/layer-diagrams-guidelines.md)합니다.  
  
 <xref:Microsoft.VisualStudio.ArchitectureTools.Extensibility.Layer> 이 항목에서 설명 하는 모델은 보다 일반적인의 단순한 버전 <xref:Microsoft.VisualStudio.GraphModel> 모델입니다. 작성 하는 경우는 [메뉴 명령 또는 제스처 확장이](../modeling/add-commands-and-gestures-to-layer-diagrams.md)를 사용 하 여는 `Layer` 모델입니다. 작성 하는 경우는 [레이어 유효성 검사 확장](../modeling/add-custom-architecture-validation-to-layer-diagrams.md), 쉽게 사용할 수는 `GraphModel`합니다.  
  
## <a name="transactions"></a>트랜잭션  
 모델을 업데이트할 때는 `ILinkedUndoTransaction`에 변경 내용을 포함할 수도 있습니다. 그러는 경우 변경 내용이 트랜잭션 하나로 그룹화됩니다. 변경 중 하나라도 실패하면 전체 트랜잭션이 롤백됩니다. 사용자가 변경 하나를 실행 취소하면 모든 변경이 함께 실행 취소됩니다.  
  
```  
using (ILinkedUndoTransaction t =  
        LinkedUndoContext.BeginTransaction("a name"))  
{   
    // Make changes here ....  
    t.Commit(); // Don't forget this!  
}  
```  
  
## <a name="containment"></a>포함  
 ![ILayer 및 ILayerModel 모두 Ilayer을 포함할 수 있습니다. ] (../modeling/media/layerapi_containment.png "LayerApi_Containment")  
  
 레이어(<xref:Microsoft.VisualStudio.ArchitectureTools.Extensibility.Layer.ILayer>) 및 레이어 모델(<xref:Microsoft.VisualStudio.ArchitectureTools.Extensibility.Layer.ILayerModel>)은 주석과 레이어를 포함할 수 있습니다.  
  
 레이어(`ILayer`)는 레이어 모델(`ILayerModel`)에 포함될 수도 있고 다른 `ILayer` 내에 중첩될 수도 있습니다.  
  
 주석이나 레이어를 만들려면 해당 컨테이너에 대해 creation 메서드를 사용합니다.  
  
## <a name="dependency-links"></a>종속성 링크  
 종속성 링크는 개체로 표시되며 양방향으로 탐색할 수 있습니다.  
  
 ![ILayerDependencyLink가 두 Ilayer를 연결 합니다. ] (../modeling/media/layerapi_dependency.png "LayerApi_Dependency")  
  
 종속성 링크를 만들려면 `source.CreateDependencyLink(target)`를 호출합니다.  
  
## <a name="comments"></a>설명  
 주석은 레이어 또는 레이어 모델에 포함될 수 있으며 레이어 요소에 연결할 수도 있습니다.  
  
 ![모든 레이어 요소에 주석은 연결할 수 있습니다. ] (../modeling/media/layerapi_comments.png "LayerApi_Comments")  
  
 원하는 수만큼의 요소에 주석을 연결하거나 아무 요소에 연결하지 않을 수도 있습니다.  
  
 레이어 요소에 연결된 주석을 가져오려면 다음 코드를 사용합니다.  
  
```csharp  
ILayerModel model = diagram.GetLayerModel();   
IEnumerable<ILayerComment> comments =   
   model.Comments.Where(comment =>   
      comment.Links.Any(link => link.Target == layerElement));  
  
```  
  
> [!CAUTION]
>  `Comments`의 `ILayer` 속성은 `ILayer` 내에 포함된 주석을 가져옵니다. 그러나 이 속성은 그에 연결된 주석은 가져오지 않습니다.  
  
 해당하는 컨테이너에서 `CreateComment()`를 호출하여 주석을 만듭니다.  
  
 주석에 대해 `CreateLink()`를 사용하여 링크를 만듭니다.  
  
## <a name="layer-elements"></a>레이어 요소  
 모델에 포함할 수 있는 모든 형식의 요소는 레이어 요소입니다.  
  
 ![종속성 다이어그램 내용이 Ilayerelement 임 ] (../modeling/media/layerapi_layerelements.png "LayerApi_LayerElements")  
  
## <a name="properties"></a>속성  
 각 `ILayerElement`에는 `Properties`라는 문자열 디렉터리가 있습니다. 이 디렉터리를 사용하여 임의의 정보를 레이어 요소에 연결할 수 있습니다.  
  
## <a name="artifact-references"></a>아티팩트 참조  
 아티팩트 참조(<xref:Microsoft.VisualStudio.ArchitectureTools.Extensibility.Layer.ILayerArtifactReference>)는 파일, 클래스, 폴더 등의 프로젝트 항목과 레이어 간 링크를 나타냅니다. 사용자 계층을 만들거나 솔루션 탐색기, 클래스 뷰 또는 개체 브라우저에서 종속성 다이어그램으로 항목을 끌어 추가할 때 아티팩트를 만듭니다. 아티팩트 참조는 원하는 수만큼 레이어에 연결할 수 있습니다.  
  
 레이어 탐색기의 각 행은 아티팩트 참조를 표시합니다. 자세한 내용은 참조 [사용자 코드에서 종속성 다이어그램을 만들](../modeling/create-layer-diagrams-from-your-code.md)합니다.  
  
 아티팩트 참조와 관련된 기본 형식 및 메서드는 다음과 같습니다.  
  
 <xref:Microsoft.VisualStudio.ArchitectureTools.Extensibility.Layer.ILayerArtifactReference>. Categories 속성은 클래스, 실행 파일, 어셈블리 등 참조되는 아티팩트의 종류를 나타내며 식별자가 대상 아티팩트를 식별하는 방법을 결정합니다.  
  
 <xref:Microsoft.VisualStudio.ArchitectureTools.Extensibility.Layer.ArtifactReferenceExtensions.CreateArtifactReferenceAsync%2A>는 <xref:EnvDTE.Project>또는 <xref:EnvDTE.ProjectItem>에서 아티팩트 참조를 만듭니다. 이 작업은 비동기 작업입니다. 그러므로 만들기가 완료되면 일반적으로 호출될 호출을 제공합니다.  
  
 레이어 아티팩트 참조를 사용 사례 다이어그램의 아티팩트와 혼동해서는 안 됩니다.  
  
## <a name="shapes-and-diagrams"></a>모양 및 다이어그램  
 레이어 모델의 각 요소를 나타내는 데 사용되는 두 개체는 <xref:Microsoft.VisualStudio.ArchitectureTools.Extensibility.Layer.ILayerElement> 및 <xref:Microsoft.VisualStudio.ArchitectureTools.Extensibility.Presentation.IShape>입니다. `IShape`는 다이어그램의 모양 크기와 위치를 나타냅니다. 레이어 모델의 모든 `ILayerElement` 개가 `IShape`, 매 `IShape` 하나 다이어그램에는 종속성에 `ILayerElement`합니다. `IShape`는 UML 모델에도 사용됩니다. 그러므로 모든 `IShape`에 레이어 요소가 있는 것은 아닙니다.  
  
 마찬가지로 <xref:Microsoft.VisualStudio.ArchitectureTools.Extensibility.Layer.ILayerModel>도 <xref:Microsoft.VisualStudio.ArchitectureTools.Extensibility.Presentation.IDiagram> 하나에 표시됩니다.  
  
 사용자 지정 명령 또는 제스처 처리기의 코드에서는 `DiagramContext` 가져오기에서 현재 다이어그램 및 현재 모양 선택을 가져올 수 있습니다.  
  
```  
public class ... {  
[Import]  
    public IDiagramContext DiagramContext { get; set; }  
...  
public void ... (...)   
{ IDiagram diagram = this.DiagramContext.CurrentDiagram;  
  ILayerModel model = diagram.GetLayerModel();  
  if (model != null)  
  { foreach (ILayer layer in model.Layers) { ... }}  
  foreach (IShape selected in diagram.SelectedShapes)  
  { ILayerElement element = selected.GetLayerElement();  
    if (element != null) ... }}  
```  
  
 ![각 ilayerelement에 대해 IShape가 표시 됨 ] (../modeling/media/layerapi_shapes.png "LayerApi_Shapes")  
  
 <xref:Microsoft.VisualStudio.ArchitectureTools.Extensibility.Presentation.IShape> 및 <xref:Microsoft.VisualStudio.ArchitectureTools.Extensibility.Presentation.IDiagram>은 UML 모델을 표시할 때도 사용됩니다. 
  
## <a name="see-also"></a>참고 항목  
 [종속성 다이어그램에 명령 및 제스처 추가](../modeling/add-commands-and-gestures-to-layer-diagrams.md)   
 [종속성 다이어그램에 사용자 지정 아키텍처 유효성 검사 추가](../modeling/add-custom-architecture-validation-to-layer-diagrams.md)   
 [종속성 다이어그램에 사용자 지정 속성 추가](../modeling/add-custom-properties-to-layer-diagrams.md)   
 [종속성 다이어그램: 참조](../modeling/layer-diagrams-reference.md)   
 [종속성 다이어그램: 지침](../modeling/layer-diagrams-guidelines.md)   
