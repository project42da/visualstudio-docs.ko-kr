---
title: "제거로 인해 ~ SAK 파일 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- temporary files
- ~sak files
- source control plug-ins, ~SAK files
ms.assetid: 5277b5fa-073b-4bd1-8ba1-9dc913aa3c50
caps.latest.revision: "15"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: e487acefcb06c4fa0cd2070bfcf20bd065d500ce
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="elimination-of-sak-files"></a>제거로 인해 ~ SAK 파일
소스 제어 플러그 인 API 1.2에는 ~ SAK 파일 기능 플래그 및 MSSCCPRJ 파일 및 공유 체크 아웃 원본 제어 플러그 인을 지원 하는지 여부를 검색 하는 새로운 기능으로 대체 되었습니다.  
  
## <a name="sak-files"></a>~ SAK 파일  
 Visual Studio.NET 2003 접두사로 추가 하는 임시 파일을 만든 ~ SAK 합니다. 이러한 파일은 소스 제어 플러그 인에서 지원 하는지 확인 하는 데 사용 됩니다.  
  
-   MSSCCPRJ 합니다. SCC 파일입니다.  
  
-   다중 체크 아웃 (공유)입니다.  
  
 플러그 인에 대해 기능을 지 원하는 고급 제공 된 소스 제어 플러그 인 API 1.2에서, IDE 새로운 기능, 플래그 및 다음 섹션에서에서 자세히 설명 하는 함수를 사용 하 여 임시 파일을 만들지 않고 이러한 기능을 검색할 수 있습니다.  
  
## <a name="new-capability-flags"></a>새 기능 플래그  
 `SCC_CAP_SCCFILE`  
  
 `SCC_CAP_MULTICHECKOUT`  
  
## <a name="new-functions"></a>새로운 함수  
 [SccWillCreateSccFile](../../extensibility/sccwillcreatesccfile-function.md)  
  
 [SccIsMultiCheckoutEnabled](../../extensibility/sccismulticheckoutenabled-function.md)  
  
 소스 제어 플러그 인 (공유) 다중 체크 아웃을 원하는 경우 다음을 선언는 `SCC_CAP_MULTICHECKOUT` 기능 및 구현 하는 `SccIsMultiCheckOutEnabled` 함수입니다. 이 함수는 소스 제어 프로젝트에서 체크 아웃 작업이 수행 될 때마다 호출 됩니다.  
  
 소스 제어 플러그 인 경우 만들고 있는 MSSCCPRJ 사용을 지원 합니다. SCC 파일 이면 선언는 `SCC_CAP_SCCFILE` 기능 및 구현 하는 [SccWillCreateSccFile](../../extensibility/sccwillcreatesccfile-function.md)합니다. 이 함수는 파일의 목록을 사용 하 여 호출 됩니다. 함수 반환 `TRUE/FALSE` 를 Visual Studio는 MSSCCPRJ을 사용할지 여부를 나타내는 각 파일에 대 한 합니다. SCC 파일 것입니다. 소스 제어 플러그 인가 이러한 새로운 기능 및 기능을 지원 하도록 하지 하는 경우 이러한 파일의 생성을 사용 하지 않도록 설정 하려면 다음 레지스트리 키를 사용할 수 있습니다.  
  
 [HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\8.0\SourceControl] "DoNotCreateTemporaryFilesInSourceControl" = dword: 00000001  
  
> [!NOTE]
>  이 레지스트리 키 dword: 00000000로 설정 되어, 있으면 되 고, 존재 하지 않는 키에 해당 하 고 Visual Studio는 여전히 임시 파일을 만들 하려고 합니다. 그러나 레지스트리 키가 dword: 00000001를 설정 하는 경우 Visual Studio 임시 파일을 만들 시도 하지 않습니다. 대신 가정 소스 제어 플러그 인은 MSSCCPRJ를 지원 하지 않습니다. SCC 파일 공유 체크 아웃을 지원 하지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 [소스 제어 플러그 인 API 버전 1.2의 새로운 기능](../../extensibility/internals/what-s-new-in-the-source-control-plug-in-api-version-1-2.md)