---
title: "자식 속성을 가진 속성 숨기기 | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "속성[Visual Studio SDK], 숨기기"
  - "속성 창, 자식 속성을 가진 속성 숨기기"
ms.assetid: 6003607e-fc19-4bf9-a299-9f6adf8e92eb
caps.latest.revision: 13
caps.handback.revision: 13
manager: "douge"
---
# 자식 속성을 가진 속성 숨기기
하위 속성이 있는 속성을 숨기고 싶은 것:  
  
-   프로젝트 중첩 된 경우에 부모 프로젝트 프로그래밍 방식으로 하위 프로젝트의 일부 측면을 제어 합니다.  
  
-   전문된 디자이너와 컨트롤을 사용 하 고 개발자가 컨트롤의 모든 속성을 모든 권한을 부여 하지 않으려는 경우.  
  
-   범위 소유 하는 개체의 한 속성의 보기를 제한 하려는 경우.  
  
### 하위 속성이 있는 속성을 숨기려면  
  
1.  Set the `pfDisplay` parameter in <xref:Microsoft.VisualStudio.Shell.Interop.IVsPerPropertyBrowsing.DisplayChildProperties%2A> to `FALSE`.  
  
2.  Set the `pfHide` parameter in <xref:Microsoft.VisualStudio.Shell.Interop.IVsPerPropertyBrowsing.HideProperty%2A> to `TRUE`.  
  
## 참고 항목  
 [눈금 표시 속성](../extensibility/internals/properties-display-grid.md)