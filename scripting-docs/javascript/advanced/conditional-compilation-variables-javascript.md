---
title: "조건부 컴파일 변수(JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords: conditional compilation, variables
ms.assetid: d6f9827d-c558-412c-8e68-de04c19c3d9d
caps.latest.revision: "11"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 900a44dab0ad418cd2899af6423f78016c90fe2b
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="conditional-compilation-variables-javascript"></a>조건부 컴파일 변수(JavaScript)
다음과 같은 미리 정의된 변수를 조건부 컴파일에 사용할 수 있습니다. 변수가 **true**가 아니면 정의되지 않으며 액세스 시 `NaN`으로 동작합니다.  
  
> [!WARNING]
>  Internet Explorer 11 이전의 모든 Internet Explorer 버전에서는 조건부 컴파일이 지원됩니다. Internet Explorer 11 표준 모드 이상 및 [!INCLUDE[win8_appname_long](../../javascript/includes/win8-appname-long-md.md)] 앱에서는 조건부 컴파일이 지원되지 않습니다.  
  
## <a name="variables"></a>변수  
  
|변수|설명|  
|--------------|-----------------|  
|@_win32|Win32 시스템에서 실행되고 있으면 True입니다.|  
|@_win16|Win16 시스템에서 실행되고 있으면 True입니다.|  
|@_mac|Apple Macintosh 시스템에서 실행되고 있으면 True입니다.|  
|@_alpha|DEC Alpha 프로세서에서 실행되고 있으면 True입니다.|  
|@_x86|Intel 프로세서에서 실행되고 있으면 True입니다.|  
|@_mc680x0|Motorola 680x0 프로세서에서 실행되고 있으면 True입니다.|  
|@_PowerPC|Motorola PowerPC 프로세서에서 실행되고 있으면 True입니다.|  
|@_jscript|항상 true입니다.|  
|@_jscript_build|[!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 스크립팅 엔진의 빌드 번호를 포함합니다.|  
|@_jscript_version|major.minor 형식의 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 버전 번호를 포함합니다.|