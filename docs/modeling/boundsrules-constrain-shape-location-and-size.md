---
title: "BoundsRules로 모양 위치 및 크기 제한 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-tfs-dev14"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "도메인별 언어, 이벤트"
ms.assetid: 4d08e541-fc67-4e68-bf31-30d346aa2aa0
caps.latest.revision: 18
caps.handback.revision: 18
author: "alancameronwills"
ms.author: "awills"
manager: "douge"
---
# BoundsRules로 모양 위치 및 크기 제한
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

A  *범위 규칙* 크기와 셰이프의 위치에 한계를 정의 하는 클래스입니다.  셰이프 모서리 또는 면 도형 사용자가 드래그 되는 동안 반복적으로 호출 되는 메서드를 제공 합니다.  
  
 다음은 직사각형의 고정 된 크기를 가로 또는 세로 막대의 수를 제한 합니다.  모서리 또는 면 사용자를 끌 때 아웃 라인 높이의 두 가지 허용 된 구성 및 너비 간의 대칭 이동 합니다.  
  
 범위 규칙을에서 클래스가 파생 됩니다 <xref:Microsoft.VisualStudio.Modeling.Diagrams.BoundsRules>.  도형에서 규칙의 인스턴스를 만듭니다.  
  
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
  
 원하는 경우의 위치와 크기를 제한 수 있습니다.  
  
## 참고 항목  
 <xref:Microsoft.VisualStudio.Modeling.Diagrams.BoundsRules>   
 [변경 내용에 대한 대응 및 전파](../modeling/responding-to-and-propagating-changes.md)