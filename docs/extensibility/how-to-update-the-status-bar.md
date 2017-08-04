---
title: "방법: 상태 표시줄 업데이트 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - update status bar
ms.assetid: 7500c8a7-4913-4818-a88b-bfd1b9887cb6
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: ca7c86466fa23fb21a932f26dc24e37c71cf29b4
ms.openlocfilehash: 15b207618487fd49516849c591ef80c56b618ce0
ms.contentlocale: ko-kr
ms.lasthandoff: 04/05/2017

---
# <a name="how-to-update-the-status-bar"></a>방법: 상태 표시줄 업데이트
**상태 표시줄** 하나 이상의 상태 텍스트 줄 또는 표시기를 포함 하는 많은 응용 프로그램 창의 맨 아래에 있는 컨트롤 막대입니다.  
  
### <a name="to-update-the-status-bar"></a>상태 표시줄을 업데이트 하려면  
  
1.  구현 <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbarUser>폼 보기와 코드 보기와 같은 편집기에서 제공 하는 각 개별 뷰 개체 (문서 뷰).</xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbarUser>  
  
2.  IDE 호출 하는 경우 <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbarUser.SetInfo%2A>, 자세한 정보는 **상태 표시줄** <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbarUser>.</xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbarUser> 의 메서드를 호출 하 여</xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbarUser.SetInfo%2A>  
  
    > [!NOTE]
    >  IDE 호출 <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbarUser.SetInfo%2A>만 문서 창이 활성화 될 때 처음.</xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbarUser.SetInfo%2A> 문서 창이 활성화 되어 시간 나머지에 대해 업데이트 해야 합니다는 **상태 표시줄** 편집기 변경의 상태와 정보입니다.  
  
## <a name="robust-programming"></a>강력한 프로그래밍  
 A **상태 표시줄** 네 개의 개별 필드가 포함 되어 있습니다.  
  
-   상태 텍스트  
  
-   진행률 표시줄  
  
-   애니메이션된 아이콘  
  
-   편집기 정보  
  
 자세한 내용은 참조 [상태 표시줄](/cpp/mfc/status-bars)합니다.  
  
 IDE를 자동으로 호출 된 <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbarUser.SetInfo%2A>메서드 프로그램 <xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbarUser>구현 문서 창이 활성화 될 때.</xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbarUser> </xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbarUser.SetInfo%2A>  
  
 VSPackage 구현 자가 상태 표시줄에 상태 텍스트를 업데이트 하는 일을 담당 합니다. IDE 상태 텍스트 필드를 빈 텍스트로로 설정 하는 경우이 문자열 "준비" 상태로 다시 설정 ("")에서 유휴 시간입니다.  
  
## <a name="see-also"></a>참고 항목  
 [상태 표시줄](/cpp/mfc/status-bars)
