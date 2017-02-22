---
title: "관리 실행 취소 및 다시 실행 하는 레거시 API를 사용 하 여 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "편집기 [Visual Studio SDK] 레거시-취소 관리"
ms.assetid: 838c0ddf-fdf3-4df1-8d21-79610b8ba0b1
caps.latest.revision: 14
caps.handback.revision: 14
ms.author: "gregvanl"
manager: "ghogen"
---
# 관리 실행 취소 및 다시 실행 하는 레거시 API를 사용 하 여
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

편집기는 사용자가 코드를 수정 하는 경우 최근 변경 내용이 되돌릴 수 있도록 실행 취소 작업을 지원 해야 합니다. 대부분의 편집기에서 구현 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 및 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 통합된 개발 환경 \(IDE\)에서 자동으로 제공 하는 작업 취소 지원을 가질 수 있습니다.  
  
## 단원 내용  
 [방법: 실행 취소 관리 구현](../extensibility/how-to-implement-undo-management.md)  
 단일 또는 다중 뷰 편집기에 대 한 실행 취소 기능을 제공합니다.  
  
 [방법: 실행 취소 스택을 지웁니다.](../extensibility/how-to-clear-the-undo-stack.md)  
 실행 취소 스택에 선택을 취소 하는 방법에 설명 합니다.  
  
 [방법: 연결 된 실행 취소 관리 사용](../extensibility/how-to-use-linked-undo-management.md)  
 편집기에 연결 된 실행 취소 관리를 통합합니다.  
  
## 참조  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsChangeTrackingUndoManager>  
 여러 뷰를 지원 하는 편집기에 대 한 실행 취소 관리를 제공 합니다.  
  
## 관련 단원