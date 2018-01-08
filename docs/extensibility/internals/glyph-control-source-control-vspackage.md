---
title: "문자 모양 제어 (소스 제어 VSPackage) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- glyphs, source control packages
- source control packages, glyphs
ms.assetid: b9413b08-b3c3-4fc3-a6e0-3dc0db3652d7
caps.latest.revision: "20"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: e41fc2a7d09f50d70caca939e3fdd691b1d05c9e
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="glyph-control-source-control-vspackage"></a>문자 모양 제어 (소스 제어 VSPackage)
소스 제어 Vspackage에 사용할 수 있는 완벽 한 통합 부분은 소스 제어에서 항목의 상태를 나타내는 고유 문자 모양을 표시 하는 기능입니다.  
  
## <a name="levels-of-glyph-control"></a>수준의 문자 모양 제어  
 상태 문자 모양 예의 표시 된 항목의 현재 상태를 나타내는 아이콘은 **솔루션 탐색기** 또는 **클래스 뷰**합니다. 소스 제어 VSPackage 두 가지 수준의 문자 모양 컨트롤을 발휘할 수 있습니다. 미리 정의 된 집합에서 제공 되는 문자의 문자 모양 선택 항목을 제한할 수는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE, 이거나 표시할 문자 모양 사용자 지정 집합을 정의할 수 있습니다.  
  
### <a name="default-set-of-glyphs"></a>문자 모양의 기본 집합  
 항목과 연결 된 상태 문자 모양의 확인 하려면 **솔루션 탐색기**를 사용 하 여 소스 제어에서 상태 문자 모양을 요청 하는 프로젝트는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccManager2.GetSccGlyph%2A>합니다. 소스 제어 VSPackage는 IDE에서 제공 하는 미리 정의 된 문자 모양의로 제한 하는 문자 모양 선택 변경 하지 않으려면 결정할 수 있습니다. 이 경우, VSPackage vsshell.idl에 정의 되는 문자 모양 열거형을 나타내는 값의 배열을 다시 전달 합니다. 자세한 내용은 참조 <xref:Microsoft.VisualStudio.Shell.Interop.VsStateIcon> 합니다. "체크 인" 문자 모양 및 "체크 아웃 됨" 문자 모양으로 확인 표시에 대 한 자물쇠 등 IDE에 의해 설정 된 문자 모양의 미리 정의 된 집합입니다.  
  
### <a name="custom-set-of-glyphs"></a>사용자 지정 문자 모양 설정  
 소스 제어 VSPackage 설치 될 때 고유 "모양과 느낌을"에 대 한 고유한 문자를 사용할 수 있습니다. 새 소스 제어 VSPackage 활성화 되 면 문자 모양이 자체 이전 소스 VSPackage를 제어 하는 경우에 아직 로드를 사용 하 여 시작할 수 있지만 비활성인 여야 합니다. 이 모드에서 소스 제어 VSPackage 여전히 צ ְ ײ 아이콘은 기존 참조와 일치 유지 하기 위해 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 필요할 경우.  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.SVsSccManager> 서비스 지원 인터페이스 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccGlyphs>를 만들며이 위해 묻습니다 IDE에 의해 만들고 VSPackage를 선택적으로 구현할 수 있습니다. IDE는 요청을 수행 하는 경우 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 차례로를 VSPackage 현재 등록 된 소스 제어에서이 인터페이스를 가져오려 시도 합니다. 인터페이스에 등록 된 VSPackage에 없는 경우 사용자 지정 문자 모양에 대 한 IDE의 요청이 성공 합니다. 그렇지 않은 경우는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE는 기본 문자 집합이 사용 합니다.  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccGlyphs.GetCustomGlyphList%2A> 메서드를 사용 하 여 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 상태를 보여주는 다양 한 소스 제어 하는 이미지의 목록을 가져옵니다. 소스 제어 VSPackage는 해당 사용자 지정 문자 모양에 대 한 이미지 목록에 대 한 핸들 IDE에 반환합니다. IDE이 시점에서 이미지 목록의 복사본을 만들어를 사용 하 여 나중에 표시할 문자 모양 선택 합니다. 새 인터페이스를 지원 하지 않는 경우 또는 `IVsSccGlyphs::GetCustomGlyphList` IDE에서 제공 되는 문자의 기본 목록에서 해당 문자를 가져오는 다음 메서드 반환 E_NOTIMPL, [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccGlyphs>   
 <xref:Microsoft.VisualStudio.Shell.Interop.VsStateIcon>   
 <xref:Microsoft.VisualStudio.Shell.Interop.SVsSccManager>