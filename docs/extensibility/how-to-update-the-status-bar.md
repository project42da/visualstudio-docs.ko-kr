---
title: "방법: 상태 표시줄 업데이트 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "편집기 [Visual Studio SDK] 레거시-상태 표시줄 업데이트"
ms.assetid: 7500c8a7-4913-4818-a88b-bfd1b9887cb6
caps.latest.revision: 12
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 12
---
# 방법: 상태 표시줄 업데이트
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

**상태 표시줄** 컨트롤 막대 상태 텍스트 줄 또는 표시기를 하나 이상 포함 된 여러 응용 프로그램 창의 아래쪽에 있습니다.  
  
### 상태 표시줄을 업데이트 하려면  
  
1.  구현 <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbarUser> 폼 보기와 코드 보기와 같은 편집기를 제공 하는 각 개별 뷰 개체 \(DocView\).  
  
2.  IDE 호출 하는 경우 <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbarUser.SetInfo%2A>의 정보 업데이트는  **상태 표시줄** 의 메서드를 호출 하 여 <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbarUser>.  
  
    > [!NOTE]
    >  IDE 호출 <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbarUser.SetInfo%2A> 에 때 문서 창의 처음에 활성화 됩니다.  나머지 문서 창의 현재 시간에 해야 하는 업데이트는  **상태 표시줄** 편집기 변경의 상태 정보입니다.  
  
## 강력한 프로그래밍  
 A  **상태 표시줄** 4 개의 별도 필드가 있습니다.  
  
-   상태 텍스트  
  
-   Progress bar  
  
-   애니메이션된 아이콘  
  
-   편집기 정보  
  
 자세한 내용은 [상태 표시줄](/visual-cpp/mfc/status-bars)를 참조하십시오.  
  
 IDE를 자동으로 호출 하는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbarUser.SetInfo%2A> 메서드를 사용자 <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbarUser> 를 문서 창이 활성화 될 때 구현.  
  
 VSPackage 구현 자가 상태 상태 표시줄에서의 텍스트를 업데이트 하는 데 담당 합니다.  상태 텍스트 필드가 빈 텍스트에 설정 된 경우이 문자열에는 "준비" IDE 다시 설정 \(""\)에 유휴 시간입니다.  
  
## 참고 항목  
 [상태 표시줄](/visual-cpp/mfc/status-bars)