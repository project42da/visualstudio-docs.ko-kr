---
title: "속성 창의 개체 목록 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Properties window, object list
ms.assetid: 6c159c9d-345d-4b23-8ddd-9839d338b62f
caps.latest.revision: "12"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: feec1e85287b3a1c24ce3c328227ba0455ae044b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="properties-window-object-list"></a>속성 창의 개체 목록
개체 목록에는 **속성** 창에 하나 이상의 선택 된 창 내에서 사용할 수 있는 다른 개체에 선택을 변경할 수 있는 드롭 다운 목록입니다. 에 대 한 호출을 트리거합니다이 목록 내에서 다른 개체를 선택 하면 <xref:Microsoft.VisualStudio.Shell.Interop.ISelectionContainer.SelectObjects%2A> 새 개체를 선택 하는 환경에 알릴 수 있습니다. 표시 되는 정보는 **속성** 창이 새로 선택 된 개체와 연결 된 속성을 표시 하려면 다음 변경 됩니다.  
  
## <a name="the-object-list"></a>개체 목록  
 두 필드의 개체 목록으로 구성 됩니다: 개체 유형과 개체 이름 (굵게 표시).  
  
 개체 자체에서 굵게 표시 된 개체 유형의 왼쪽에 표시 개체 이름을 검색 하는 사용 하 여는 `Name` 속성에서 제공 되는 <xref:Microsoft.VisualStudio.OLE.Interop.IProvideClassInfo> 인터페이스입니다. <xref:Microsoft.VisualStudio.OLE.Interop.IProvideClassInfo.GetClassInfo%2A>에 유일한 방법은 <xref:Microsoft.VisualStudio.OLE.Interop.IProvideClassInfo>, 반환 <xref:Microsoft.VisualStudio.OLE.Interop.ITypeInfo> 해당 인터페이스의 coclass에 대 한 합니다. **속성** 창을 사용 하 여 <xref:Microsoft.VisualStudio.OLE.Interop.IProvideClassInfo> 드롭 다운 목록에서 개체 이름을로 표시 되는 coclass의 이름을 가져올 수 있습니다.  
  
 개체에 없는 경우는 `Name` 속성 이름을 개체 목록의 이름 영역에 표시 되지 않습니다. 개체 목록에 표시 되는 이름을 사용 하려는 경우 개체에는 Name 속성을 추가할 수 있습니다.  
  
 COM 개체를 구현 하지 않는 경우 <xref:Microsoft.VisualStudio.OLE.Interop.IProvideClassInfo>, **속성** 목록의 왼쪽에서 인터페이스 이름 대신 개체 이름 창에 표시 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [속성 확장](../../extensibility/internals/extending-properties.md)