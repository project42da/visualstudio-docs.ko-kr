---
title: BoundsRules 셰이프 위치와 크기를 제한 합니다. | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.topic: article
helpviewer_keywords:
- Domain-Specific Language, events
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: c672cbc25c28bf4d74f01160212584875b51ba1a
ms.sourcegitcommit: 3b692c9bf332b7b9150901e16daf99a64b599fee
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/10/2018
---
# <a name="boundsrules-constrain-shape-location-and-size"></a>BoundsRules로 모양 위치 및 크기 제한
A *범위 규칙* 도형의 위치와 크기에 제한을 정의 하는 클래스입니다. 사용자가 셰이프 또는 모서리나 측면 도형의 끌고 동안 반복적으로 호출 되는 메서드를 제공 합니다.  
  
 다음 예제에서는 직사각형의 고정 된 크기를 가로 또는 세로 막대 수를 제한 합니다. 사용자가 모서리나 측면을 끌면 개요의 너비와 높이의 두 가지 허용 된 구성 간의 대칭 이동 합니다.  
  
 범위 규칙 클래스에서 파생 <xref:Microsoft.VisualStudio.Modeling.Diagrams.BoundsRules>합니다. 도형에 규칙의 인스턴스를 만듭니다.  
  
```  
using Microsoft.VisualStudio.Modeling.Diagrams; ...  
public partial class BarShape  
{  
  /// <summary>  
  /// Rule invoked when the user is resizing a shape.  
  /// </summary>  
  public override BoundsRules BoundsRules  
  { get { return new BarBoundsRule(); } }  
}  
/// <summary>  
/// Rule invoked when the user is changing a shape's outline.  
/// Provides real-time mouse rubber-band feedback, so must work fast.  
/// </summary>  
public class BarBoundsRule: BoundsRules  
{   
  public override RectangleD GetCompliantBounds   
     (ShapeElement shape, RectangleD proposedBounds)  
  {  
    double thickness = 0.1;  
    if (proposedBounds.Height > proposedBounds.Width)  
    {  
      // There is a minimum width for a shape; the width  
      // will actually be set to the lesser of   
      // thickness and that minimum.  
      return new RectangleD(proposedBounds.Location,   
            new SizeD(thickness, proposedBounds.Height));  
    }  
    else  
    {  
      // There is a minimum height for a shape; the   
      // height will actually be set to the lesser of   
      // thickness and that minimum.  
      return new RectangleD(proposedBounds.Location,   
         new SizeD(proposedBounds.Width, thickness));  
} } }  
```  
  
 확인 하려는 경우 위치 및 크기 수 제한 합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualStudio.Modeling.Diagrams.BoundsRules>   
 [변경 내용에 대한 대응 및 전파](../modeling/responding-to-and-propagating-changes.md)