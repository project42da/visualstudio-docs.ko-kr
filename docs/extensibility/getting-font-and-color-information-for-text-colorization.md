---
title: "글꼴 및 색상 정보가 텍스트 색 지정에 대 한 가져오기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- text, coloring
- font and color control [Visual Studio SDK], coloring
ms.assetid: d1f985bd-743e-40b7-9458-d9af53647c91
caps.latest.revision: "22"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: e3b31ad2ec080070dec3c68b304f400d204d47a0
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="getting-font-and-color-information-for-text-colorization"></a>글꼴 및 텍스트 색 지정에 대 한 색상 정보 가져오기
렌더링 또는 사용자 인터페이스 (UI) 요소에 컬러로 텍스트를 표시 하는 프로세스 프로젝트, 기술 및 개발자 환경 설정의 유형에 따라 달라 집니다. **글꼴 및 색** 속성 페이지 설정을 저장 합니다.  
  
 으로 지정된 하는 텍스트를 표시 하는 대부분의 구현에 필요는 `T:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorDefaults` 제시, 검색 및 텍스트를 저장할 표시 설정에 대 한 인터페이스를 연결 합니다.  
  
> [!NOTE]
>  코어 편집기 사용자 지정 하는 경우 (지 원하는 **텍스트 EditorCategory**), 언어 서비스에서 색 지정 기술을 사용 하는 것이 좋습니다. 자세한 내용은 참조 [글꼴 및 색 개요](../extensibility/font-and-color-overview.md)합니다.  
  
## <a name="getting-default-font-and-color-information"></a>기본 글꼴 및 색 정보 가져오기  
 모든는 **글꼴 및 색** 텍스트를 표시 하는 모든 창의 설정으로 지정 해야는 **표시 항목** 하나의 **범주**합니다. 자세한 내용은 참조 [글꼴 및 색, 환경, 옵션 대화 상자](../ide/reference/fonts-and-colors-environment-options-dialog-box.md)합니다.  
  
 VSPackage, 색을 지정 하려면 현재를 받아야 합니다 **글꼴 및 색** 설정 합니다. VSPackage는 다음과 같은 방법으로 요구 사항에 따라이 수행할 수 있습니다.  
  
-   글꼴 및 색 지 속성 메커니즘을 사용 하 여 저장 또는 현재 상태를 검색 합니다. 자세한 내용은 참조 [에 액세스 하는 저장 된 글꼴 및 색 설정](../extensibility/accessing-stored-font-and-color-settings.md)합니다.  
  
-   사용 하 여는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorDefaultsProvider> 글꼴 및 색 데이터의 인스턴스를 제공 하는 서비스의 인터페이스 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorDefaults>VSPackage 글꼴 및 색 공급자 아닌 경우, 합니다.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorEvents> 인터페이스를 구현합니다.  
  
 하는지를 확인 하기 위해 폴링을 통해 얻은 결과 최신을 사용 하면 유용할 수 있습니다는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorCacheManager> 의 검색 메서드를 호출 하기 전에 필요한는 업데이트를 확인 하는 인터페이스는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorStorage> 인터페이스입니다.  
  
 얻은 후 글꼴 및 색 정보, 색 지정을 요구 하는 요소를 식별 하 게 표시 될 텍스트를 구문 분석 및 적절 한 글꼴 및 색을 사용 하 여 창에 텍스트를 표시 합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorDefaultsProvider>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorDefaults>   
 [글꼴 및 텍스트를 사용 하 여](/dotnet/framework/winforms/advanced/using-fonts-and-text)   
 [색 작업](/cpp/windows/working-with-color-image-editor-for-icons)   
 [GDI (그래픽 장치 인터페이스)](http://msdn.microsoft.com/en-us/7e1d4540-bb2e-4257-8eee-eee376acba83)