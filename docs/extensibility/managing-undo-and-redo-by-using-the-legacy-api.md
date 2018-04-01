---
title: 실행 취소 관리와 레거시 API를 사용 하 여 다시 실행 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - undo management
ms.assetid: 838c0ddf-fdf3-4df1-8d21-79610b8ba0b1
caps.latest.revision: 14
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: c50316b7d5786b1fb3f07255eaf4d875f7f41e5b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="managing-undo-and-redo-by-using-the-legacy-api"></a>실행 취소 관리와 레거시 API를 사용 하 여 다시 실행
편집기는 사용자가 코드를 수정 하는 경우 최근 변경 내용이 되돌릴 수 있도록 실행 취소 작업을 지원 해야 합니다. 대부분의 편집기에서 구현 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 및 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 통합된 개발 환경 (IDE)에서 자동으로 제공 하는 실행 취소 지원을 가질 수 있습니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [방법: 실행 취소 관리 구현](../extensibility/how-to-implement-undo-management.md)  
 단일 또는 여러 뷰가 있는 편집기에 대 한 실행 취소 기능을 제공합니다.  
  
 [방법: 실행 취소 스택을 지웁니다.](../extensibility/how-to-clear-the-undo-stack.md)  
 실행 취소 스택에 선택을 취소 하는 방법에 설명 합니다.  
  
 [방법: 연결 된 실행 취소 관리 사용](../extensibility/how-to-use-linked-undo-management.md)  
 편집기에 연결 된 실행 취소 관리를 통합합니다.  
  
## <a name="reference"></a>참조  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsChangeTrackingUndoManager>  
 여러 뷰를 지원 하는 편집기에 대 한 실행 취소 관리를 제공 합니다.  
  
## <a name="related-sections"></a>관련 단원