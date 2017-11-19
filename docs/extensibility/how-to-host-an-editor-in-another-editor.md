---
title: "방법: 다른 편집기에서 편집기를 호스팅할 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: editors [Visual Studio SDK], legacy - host a nested editor
ms.assetid: 2b0eb705-fe94-4ca8-93e0-9dbd8ce61a44
caps.latest.revision: "14"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 26819cccc4f5359da83684575423f8d0be276497
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-host-an-editor-in-another-editor"></a>방법: 다른 편집기에서 편집기를 호스트 합니다.
Visual Studio에서 호스팅 창의 부모 창으로 지정 하 여 다른 한 편집기를 호스트할 수 있습니다. 이렇게 하려면 매개 변수를 설정할 <xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID2> 및 <xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID2> 자식 창 프레임에 있습니다.  
  
### <a name="to-set-up-the-window-frame-to-host-an-editor"></a>편집기를 호스팅하는 창 프레임을 설정 하려면  
  
1.  자식 창 창을 만들어 호스팅된 편집기로 편집기를 지정 합니다.  
  
     이 창은 편집기의 텍스트를 이동 합니다.  
  
2.  사용 하 여 호스팅 편집기 만들기는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A> 또는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenSpecificEditor%2A> 메서드.  
  
3.  설정의 <xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID2> 및 <xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID2> 이러한 속성에 대 한 매개 변수로 전달 하 여 호스트 된 편집기의 프레임 창 구현에서 속성의 <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame.SetProperty%2A> 메서드를 각각.  
  
     이러한 매개 변수를 검색 해야 하는 경우이 속성에 전달 된 <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame.GetProperty%2A> 메서드.  
  
4.  호출 된 <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame.Show%2A> 포함 된 편집기에 대 한 메서드.  
  
     편집기는 포함 하 여 편집기의 호스트 창에 나타납니다.  
  
## <a name="robust-programming"></a>강력한 프로그래밍  
 **응용 프로그램 디자이너** 설계자를 위해 Visual Studio Team Edition에는 다른 편집기를 호스팅하는 편집기 창 프레임의 예시입니다. **응용 프로그램 디자이너** 다른 디자이너의 오른쪽 창에 호스팅합니다. 디자이너 패널 (또는 **속성** 페이지)에 포함 된 디자이너의 각 포함 된 창 프레임에 추가 됩니다.