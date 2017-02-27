---
title: "방법: 다른 편집기에서 편집기를 호스트 합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "편집기 [Visual Studio SDK]-레거시 호스트 중첩된 편집기는"
ms.assetid: 2b0eb705-fe94-4ca8-93e0-9dbd8ce61a44
caps.latest.revision: 14
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 14
---
# 방법: 다른 편집기에서 편집기를 호스트 합니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Visual Studio 호스팅 창의 부모 창으로 지정 하 여 다른 편집기를 호스팅할 수 있습니다.  매개 변수를 설정 <xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID2> 및 <xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID2> 자식 창 프레임입니다.  
  
### 편집기를 호스트 하는 창 프레임을 설정 하려면  
  
1.  자식 창의 창 작성 하 여 호스팅된 편집기로 편집기를 지정 합니다.  
  
     이 창의 텍스트 편집기의 위치입니다.  
  
2.  호스팅 편집기를 사용 하 여 만들는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A> 또는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenSpecificEditor%2A> 방법입니다.  
  
3.  설정의 <xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID2> 및 <xref:Microsoft.VisualStudio.Shell.Interop.__VSFPROPID2> 속성 창 프레임 구현에서는 이러한 속성을 매개 변수로 전달 하 여 호스팅된 편집기는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame.SetProperty%2A> 메서드를 각각.  
  
     이러한 매개 변수를 검색 하는 경우 해당이 속성에 전달의 <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame.GetProperty%2A> 메서드가 있습니다.  
  
4.  호출 하는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame.Show%2A> 메서드는 포함 된 편집기를 합니다.  
  
     편집기는 호스팅된 포함 하 여 편집기 창에 표시 됩니다.  
  
## 강력한 프로그래밍  
 해당  **응용 프로그램 디자이너** Visual Studio Team Edition에 대 한 설계자의 다른 편집기를 호스팅하는 편집기 창 프레임 예제입니다.  해당  **응용 프로그램 디자이너** 다른 디자이너의 오른쪽 창에서 호스트 됩니다.  디자이너 패널 \(또는  **속성이** 페이지\) 각각에 포함 된 디자이너에 포함 된 창 프레임에 대해.