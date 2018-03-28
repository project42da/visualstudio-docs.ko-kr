---
title: 언어를 포함 합니다. | Microsoft Docs
ms.date: 03/22/2018
ms.technology:
- vs-ide-sdk
ms.topic: article
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - contained languages
ms.assetid: b75bbb51-8e42-41b1-bece-09ab0b1f03cc
caps.latest.revision: ''
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 7ec180689f4dadfb60832259ddee51a05f336fda
ms.sourcegitcommit: 768118d470da9c7164d2f23ca918dfe26a4be72f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/28/2018
---
# <a name="contained-languages"></a>포함 된 언어

*언어에 포함 된* 는 다른 언어에 포함 되는 언어입니다. 예를 들어 HTML [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 포함할 수도 있습니다 [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] 또는 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 스크립트입니다. 이중 언어 아키텍처는 HTML 및 스크립트 언어를 모두에 대 한 IntelliSense, 색 지정, 및 기타 편집 기능을 제공 하는.aspx 파일 편집기 필요 합니다.

## <a name="implementation"></a>구현

포함 된 언어에 대 한 구현에 필요한 가장 중요 한 인터페이스는는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsContainedLanguage> 인터페이스입니다. 이 인터페이스는 र ा थ 내 호스팅될 수 있는 모든 언어로 구현 됩니다. 언어 서비스의 색 지정 기, 텍스트 보기 필터 및 र ा थ 서비스 ID에 대 한 액세스 부여 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsContainedLanguageFactory> 만들 수 있습니다는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsContainedLanguage> 인터페이스입니다. 다음 단계는 포함 된 언어를 구현 하는 방법을 보여 줍니다.

1.  사용 하 여 `QueryService()` 언어의 인터페이스 ID와 서비스 ID를 가져옵니다는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsContainedLanguageFactory>합니다.

2.  만들려는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsContainedLanguage> 인터페이스를 호출 하는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsContainedLanguageFactory.GetLanguage%2A> 메서드. 전달 된 <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> 인터페이스를 하나 이상의 [항목 Id](<xref:Microsoft.VisualStudio.VSConstants.VSITEMID>), 및 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBufferCoordinator> 인터페이스입니다.

3.  <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBufferCoordinator> 인터페이스 텍스트 버퍼 코디네이터 개체를 보조 언어의 버퍼에 주 파일의 위치를 매핑하는 데 필요한 기본 서비스를 제공 합니다.

     예를 들어 단일.aspx 파일은 주 파일에는 ASP, HTML 및 포함 된 모든 코드가 포함 됩니다. 그러나 보조 버퍼에는 모든 클래스 정의 파일을 만들기 위해 보조 버퍼는 올바른 코드와 함께 포함 된 코드만 포함 되어 있습니다. 버퍼 코디네이터 처리 하는 작업을 조정 하 고 다른에 대 한 버퍼에서 편집 합니다.

4.  <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBufferCoordinator.SetSpanMappings%2A> 메서드는 기본 언어를 보조 버퍼에서 해당 텍스트에 매핑된 해당 버퍼 내에서 텍스트 버퍼 코디네이터 지시 합니다.

     언어의 배열에서 전달는 <xref:Microsoft.VisualStudio.TextManager.Interop.NewSpanMapping> 현재 기본 및 보조 범위만 포함 하는 구조입니다.

5.  <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBufferCoordinator.MapPrimaryToSecondarySpan%2A> 메서드 및 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBufferCoordinator.MapSecondaryToPrimarySpan%2A> 메서드 보조 버퍼로 그리고 반대로 기본 매핑을 제공 합니다.