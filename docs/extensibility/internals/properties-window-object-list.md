---
title: "속성 창의 개체 목록 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "속성 창에서 개체 목록"
ms.assetid: 6c159c9d-345d-4b23-8ddd-9839d338b62f
caps.latest.revision: 12
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 12
---
# 속성 창의 개체 목록
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

개체 목록에 있는  **속성** 창 선택 하나 이상의 선택한 windows 내에서 사용할 수 있는 다른 개체를 변경할 수 있는 드롭다운 목록입니다.  이 목록에서 다른 개체를 선택 하면 호출을 트리거합니다 <xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer.SelectObjects%2A> 환경 새 개체를 선택 했음을 알리기 위해.  에 표시 되는 정보를  **속성** 창을 새로 선택한 개체와 관련 된 속성을 표시 하려면 변경 되 고 있습니다.  
  
## 개체 목록  
 개체 목록에 두 개의 필드로 구성 됩니다. \(굵게 표시\) 개체 이름 및 개체 형식입니다.  
  
 왼쪽에 굵게 표시 된 개체 형식의 표시 되는 개체 이름을 개체에서 검색 되 사용 하는 `Name` 에서 제공 하는 속성의 <xref:Microsoft.VisualStudio.OLE.Interop.IProvideClassInfo> 인터페이스.  <xref:Microsoft.VisualStudio.OLE.Interop.IProvideClassInfo.GetClassInfo%2A>을 하는 유일한 방법에 <xref:Microsoft.VisualStudio.OLE.Interop.IProvideClassInfo>, 반환 <xref:Microsoft.VisualStudio.OLE.Interop.ITypeInfo> 인터페이스의 coclass에 대 한.  **속성** 창을 사용 하 여 <xref:Microsoft.VisualStudio.OLE.Interop.IProvideClassInfo> 개체 이름 드롭다운 목록에 표시 되는 coclass의 이름을 가져올 수 있습니다.  
  
 개체에 게는 `Name` 는 name 속성 개체 목록 이름 영역에 표시 되지 않습니다.  개체 목록에 표시 되는 이름을 원하는 경우 Name 속성을 개체에 추가할 수 있습니다.  
  
 COM 개체를 구현 하지 않는 경우 <xref:Microsoft.VisualStudio.OLE.Interop.IProvideClassInfo>, the  **속성이** 창 인터페이스 이름 개체 이름 대신 왼쪽 목록에 표시 됩니다.  
  
## 참고 항목  
 [속성 확장](../../extensibility/internals/extending-properties.md)