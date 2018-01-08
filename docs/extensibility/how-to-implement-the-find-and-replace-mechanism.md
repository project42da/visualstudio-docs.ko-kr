---
title: "방법: 찾기 구현 및 메커니즘을 바꾸기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editors [Visual Studio SDK], legacy - find and replace
ms.assetid: bbd348db-3d19-42eb-99a2-3e808528c0ca
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: c971d4565c95cab23e683a1a4f20c75ebea81b8f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-implement-the-find-and-replace-mechanism"></a>방법: 찾기 구현 및 메커니즘을 바꾸기
Visual Studio 찾기/바꾸기를 구현 하는 두 가지를 제공 합니다. 한 가지 방법은 텍스트 이미지 셸에 전달할 검색, 강조 표시 및 바꿀 텍스트를 처리 하도록 합니다. 따라서 사용자가 여러 텍스트 범위를 지정할 수 있습니다. 또는, VSPackage 자체에서 이러한 기능을 제어할 수 있습니다. 두 경우 모두 현재 대상과 열려 있는 모든 문서에 대 한 대상으로 하는 방법에 대 한 셸에 알려야 합니다.  
  
### <a name="to-implement-findreplace"></a>찾기/바꾸기를 구현 하려면  
  
1.  구현 된 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget> 프레임 속성에서 반환 된 개체 중 하나에서 인터페이스 <xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID> 또는 <xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID>합니다. 사용자 지정 편집기를 만드는 경우에 사용자 지정 편집기 클래스의 일부로이 인터페이스를 구현 해야 합니다.  
  
2.  사용 된 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.GetCapabilities%2A> 메서드 편집기 지원 옵션을 지정 하 고 텍스트 이미지 검색 구현 여부를 나타냅니다.  
  
     편집기 텍스트 이미지 검색을 지 원하는 경우 구현 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.GetSearchImage%2A>합니다.  
  
     그렇지 않은 경우 구현 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.Find%2A> 및 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.Replace%2A>합니다.  
  
3.  구현 하는 경우는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.Find%2A> 및 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.Replace%2A> 메서드를 호출 하 여 검색 작업을 간소화할 수 있습니다는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindHelper> 인터페이스입니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindHelper>   
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget>   
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.Find%2A>   
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.GetSearchImage%2A>   
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsFindTarget.Replace%2A>   
 <xref:Microsoft.VisualStudio.Shell.Interop.__VSPROPID>