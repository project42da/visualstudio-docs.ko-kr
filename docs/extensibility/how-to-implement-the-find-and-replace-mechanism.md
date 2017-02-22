---
title: "방법: 구현 찾기 및 바꾸기 메커니즘 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "편집기 [Visual Studio SDK] 레거시-찾기 및 바꾸기"
ms.assetid: bbd348db-3d19-42eb-99a2-3e808528c0ca
caps.latest.revision: 11
caps.handback.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
---
# 방법: 구현 찾기 및 바꾸기 메커니즘
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Visual Studio 찾기\/바꾸기를 구현 하는 두 가지 방법을 제공 합니다.  텍스트 이미지를 셸에 전달 하 여 검색 하 고 강조 표시 하 고 대체 텍스트를 처리할 수 있습니다.  이 사용자가 여러 텍스트 범위를 지정할 수 있습니다.  또한 Vspackage를이 기능을 제어할 수 있습니다.  두 경우 모두 현재 대상 및 열려 있는 모든 문서에 대 한 대상에 대 한 셸에 알려야 합니다.  
  
### 찾기\/바꾸기 구현 하기  
  
1.  구현에서 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget> 인터페이스 프레임 속성에 의해 반환 되는 개체 중 하나에서 <xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID> 또는 <xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID>.  사용자 지정 편집기를 만드는 경우이 인터페이스는 사용자 지정 편집기 클래스의 일부로 구현 해야 합니다.  
  
2.  사용은 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.GetCapabilities%2A> 메서드 편집기에서 지 원하는 옵션을 지정 하 고 텍스트 이미지 검색 구현 하는지 여부를 나타냅니다.  
  
     이미지를 검색 하는 텍스트를 편집기를 지 원하는 경우 구현 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.GetSearchImage%2A>.  
  
     그렇지 않으면, 구현 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.Find%2A> 및 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.Replace%2A>.  
  
3.  구현 하는 경우는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.Find%2A> 및 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.Replace%2A> 메서드를 호출 하 여 검색 작업을 단순화할 수 있습니다의 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindHelper> 인터페이스입니다.  
  
## 참고 항목  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindHelper>   
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget>   
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.Find%2A>   
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.GetSearchImage%2A>   
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.Replace%2A>   
 <xref:Microsoft.VisualStudio.Shell.Interop.__VSPROPID>