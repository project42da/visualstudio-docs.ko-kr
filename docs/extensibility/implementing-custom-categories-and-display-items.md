---
title: "사용자 지정 범주 및 표시 항목 구현 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- font and color control [Visual Studio SDK], categories
- custom categories
ms.assetid: 99311a93-d642-4344-bbf9-ff6e7fa5bf7f
caps.latest.revision: "25"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: f03dbae8b320161705c50da06d605cfc335074cc
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="implementing-custom-categories-and-display-items"></a>사용자 지정 범주를 구현 하는 항목 표시
글꼴의 제어 및 해당 텍스트의 색 VSPackage를 제공할 수는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 사용자 지정 범주 및 표시 항목을 통해 통합된 개발 환경 (IDE).  
  
 사용자 지정 범주와 표시 항목에 있는 **글꼴 및 색** 속성 페이지. 열려는 **글꼴 및 색** 속성 페이지는 **도구** 메뉴를 클릭 **옵션**합니다. 확장 **환경** 클릭 하 고 **글꼴 및 색**합니다.  
  
 이 메커니즘을 사용할 경우 Vspackage를 구현 해야 합니다는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorDefaultsProvider> 인터페이스와 연결 된 해당 인터페이스입니다.  
  
 기본적으로이 메커니즘 데 사용할 수 모든 기존 수정 **항목 표시** 및 **범주** 포함 하는 합니다. 그러나 하지 사용 해야 수정 하는 **텍스트 EditorCategory** 나 해당 **항목 표시**합니다. 자세한 내용은 참조 [글꼴 및 색 개요](../extensibility/font-and-color-overview.md)합니다.  
  
 사용자 지정을 구현 하려면 **범주** 또는 **항목 표시**, VSPackage 해야 합니다.  
  
-   만들거나 레지스트리에 범주를 식별 합니다.  
  
     구현에서 IDE의는 **글꼴 및 색** 속성 페이지에서이 정보를 사용 하 여 올바르게 지정된 된 범주를 지 원하는 서비스에 대 한 쿼리 합니다.  
  
-   만들거나 레지스트리에 지정 된 그룹 (선택 사항)을 식별 합니다.  
  
     두 개 이상의 범주의 합집합을 나타내는 그룹 정의에 유용할 수 있습니다. 그룹을 정의 하는 경우 IDE 자동으로 병합 하는 하위 범주 고이 배포 그룹 내에서 항목을 표시 합니다.  
  
-   IDE 지원을 구현 합니다.  
  
-   글꼴 및 색 변경 내용을 처리 합니다.  
  
 자세한 내용은 참조 [에 액세스 하는 저장 된 글꼴 및 색 설정](../extensibility/accessing-stored-font-and-color-settings.md)합니다.  
  
## <a name="to-create-or-identify-categories"></a>만들거나 범주를 확인 하려면  
  
-   아래에 레지스트리 항목 범주에는 특수 한 유형의 생성 [HKLM\SOFTWARE\Microsoft \Visual Studio\\*\<Visual Studio 버전 >*\FontAndColors\\`<Category>`]  
  
     *\<범주 >* 범주의 지역화 되지 않은 이름입니다.  
  
-   두 값을 사용 하 여 레지스트리를 채웁니다.  
  
    |이름|형식|데이터|설명|  
    |----------|----------|----------|-----------------|  
    |범주|REG_SZ|GUID|만든 범주를 식별 하는 GUID입니다.|  
    |패키지|REG_SZ|GUID|범주를 지 원하는 VSPackage 서비스의 GUID입니다.|  
  
 레지스트리에 지정 된 서비스의 구현을 제공 해야 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorDefaults> 해당 범주에 대 한 합니다.  
  
## <a name="to-create-or-identify-groups"></a>만들거나 그룹 식별  
  
-   아래에 레지스트리 항목 범주에는 특수 한 유형의 생성 [HKLM\SOFTWARE\Microsoft \Visual Studio\\*\<Visual Studio 버전 >*\FontAndColors\\  *\<그룹 >*]  
  
     *\<그룹 >* 그룹의 지역화 되지 않은 이름입니다.  
  
-   두 값을 사용 하 여 레지스트리를 채웁니다.  
  
    |이름|형식|데이터|설명|  
    |----------|----------|----------|-----------------|  
    |범주|REG_SZ|GUID|그룹을 식별 하기 위해 생성 하는 GUID입니다.|  
    |패키지|REG_SZ|GUID|범주를 지 원하는 서비스의 GUID입니다.|  
  
 레지스트리에 지정 된 서비스의 구현을 제공 해야 `T:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorGroup` 해당 그룹에 대 한 합니다.  
  
## <a name="to-implement-ide-support"></a>IDE 지원 기능을 구현 하려면  
  
-   구현 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorDefaultsProvider.GetObject%2A>, 반환 하는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorDefaults> 인터페이스 또는 `T:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorGroup` 인터페이스 각각에 대 한 IDE **범주** 하거나 제공 된 GUID를 그룹화 합니다.  
  
-   에 대 한 모든 **범주** 지원, 별도의 인스턴스를 구현 하는 VSPackage는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorDefaults> 인터페이스입니다.  
  
-   메서드를 통해 구현 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorDefaults> 있는 IDE를 제공 해야 합니다.  
  
    -   목록에 **항목 표시** 에 **범주입니다.**  
  
    -   에 대 한 지역화 가능한 이름을 **항목 표시**합니다.  
  
    -   각 멤버에 대 한 정보를 표시 **범주**합니다.  
  
    > [!NOTE]
    >  모든 **범주** 하나 이상 포함 해야 **표시 항목**합니다.  
  
-   사용 하 여 IDE는 `T:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorGroup` 여러 종류의 합집합을 정의 하는 인터페이스입니다.  
  
     구현을 사용 하 여 IDE를 제공합니다.  
  
    -   목록은 **범주** 지정된 된 그룹을 구성 하는 합니다.  
  
    -   인스턴스에 대 한 액세스 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorDefaults> 지 원하는 각 **범주** 그룹 내에서.  
  
    -   지역화할 수 있는 그룹 이름입니다.  
  
-   IDE를 업데이트 하는 중:  
  
     IDE에 대 한 정보를 캐시 **글꼴 및 색** 설정 합니다. 따라서 IDE의 수정한 다음 **글꼴 및 색** 구성 않는 것이 좋습니다 캐시가 최신 상태 인지 확인 합니다.  
  
 통해 수행 되는 캐시를 업데이트 하는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorCacheManager> 인터페이스를 전역으로 또는 있는 것이 아니라 선택 된 항목으로 수행된 될 수 있습니다.  
  
## <a name="to-handle-font-and-color-changes"></a>핸들 글꼴 및 색 변경  
 VSPackage를 표시 하는 텍스트의 색 지정을 올바르게 지원 하려면 VSPackage를 지 원하는 색 지정 서비스를 통해 사용자가 시작한 변경에 응답 해야는 **글꼴 및 색** 속성 페이지. VSPackage이 수행합니다.  
  
-   구현 하 여 IDE에서 생성 된 이벤트를 처리는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorEvents> 인터페이스입니다.  
  
     사용자 수정 사항에 따라 적절 한 메서드를 호출 하는 IDE는 **글꼴 및 색** 페이지. 예를 들어 호출는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorEvents.OnFontChanged%2A> 메서드 새 글꼴을 선택 합니다.  
  
     또는  
  
-   변경 내용에 대 한 IDE를 폴링합니다.  
  
     시스템 구현를 통해 이렇게 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorStorage> 인터페이스입니다. 지 속성 지원을 위해 주로 있지만 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorStorage.GetItem%2A> 메서드에 대 한 글꼴 및 색 정보를 가져오는 데 사용할 수 있습니다 **항목 표시**합니다. 자세한 내용은 참조 [에 액세스 하는 저장 된 글꼴 및 색 설정](../extensibility/accessing-stored-font-and-color-settings.md)합니다.  
  
    > [!NOTE]
    >  올바른 폴링을 통해 얻은 결과 위해이을 사용 하면 유용할 수 있습니다는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorCacheManager> 의 검색 메서드를 호출 하기 전에 캐시 플러시 및 업데이트는 필요한 경우를 확인 하는 인터페이스는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorStorage> 인터페이스입니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider.QueryService%2A>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorDefaults>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorEvents>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorStorage>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorGroup>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorDefaultsProvider>   
 [글꼴 및 텍스트 색 지정에 대 한 색상 정보 가져오기](../extensibility/getting-font-and-color-information-for-text-colorization.md)   
 [저장 된 글꼴 및 색 설정에 액세스](../extensibility/accessing-stored-font-and-color-settings.md)   
 [방법: 기본 제공 글꼴 및 색 구성표에 액세스](../extensibility/how-to-access-the-built-in-fonts-and-color-scheme.md)   
 [글꼴 및 색 개요](../extensibility/font-and-color-overview.md)