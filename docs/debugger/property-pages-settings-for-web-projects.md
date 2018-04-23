---
title: 속성 페이지 웹 프로젝트에 대 한 설정 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging [Visual Studio], Web applications
- project settings [Visual Studio], debug configurations
- debug builds, project settings
- projects [Visual Studio], debug configurations
- debugging Web applications, project settings
- debug configurations, Web projects
ms.assetid: 8ec5160a-6408-4f47-8d41-f0e20e79a3b9
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0e2559ad8e1c2d233ffcb1873b0f7f5212bd6cf7
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="property-pages-settings-for-web-projects"></a>웹 프로젝트에 대한 속성 페이지 설정
웹 사이트 디버그 구성에 대 한 속성 설정을 변경할 수 있습니다는 **속성 페이지** 대화 상자에 설명 된 대로 [디버그 및 릴리스 구성](../debugger/how-to-set-debug-and-release-configurations.md)합니다. 다음 표에에서 디버거 관련 설정을 확인할 수 있는 위치는 **속성 페이지** 대화 상자.  
  
### <a name="configuration-properties-folder-start-options-category"></a>구성 속성 폴더(시작 옵션 범주)  
  
|**설정**|**설명**|  
|-----------------|---------------------|  
|**시작 작업**|응용 프로그램 시작에 관련된 옵션을 그룹화하는 제목입니다.|  
|**현재 페이지를 사용 하 여**|현재 페이지를 디버깅의 시작 위치로 지정합니다.|  
|**특정 페이지:**|디버깅을 시작할 웹 페이지를 지정합니다.|  
|**시작 외부 프로그램:**|디버그 대상 프로그램을 실행하는 명령을 지정합니다.|  
|**명령줄 인수:**|위에서 지정한 명령의 인수를 지정합니다.|  
|**작업 디렉터리:**|디버깅 중인 프로그램의 작업 디렉터리를 지정합니다. [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)]에서는 응용 프로그램이 시작된 디렉터리가 작업 디렉터리입니다. 이 디렉터리는 기본적으로 \bin\debug입니다.|  
|**시작 URL**|디버깅할 웹 응용 프로그램의 위치를 지정합니다.|  
|**페이지를 열지 않고 외부 응용 프로그램의 요청 기다리기**|외부 응용 프로그램의 요청을 기다리도록 지정합니다. 이 옵션은 Internet Explorer 또는 다른 응용 프로그램을 시작하지 않습니다. 응용 프로그램에서 호출될 때 디버깅이 준비합니다.|  
|**서버**|사용할 서버에 관련된 옵션을 그룹화하는 제목입니다.|  
|**기본 웹 서버 사용**|기본 웹 서버를 사용하도록 지정합니다.|  
|**사용자 지정 서버 사용**|서버로 사용할 기본 URL을 입력할 수 있습니다.|  
|**디버거**|수행할 디버깅의 형식에 관련된 옵션을 그룹화하는 제목입니다.|  
|**ASP.NET 디버깅**|[!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 개발 플랫폼용으로 작성된 서버 페이지를 디버깅할 수 있습니다. URL을 지정 해야 **시작 URL**합니다.|  
|**네이티브 코드 디버깅**|관리되는 응용 프로그램에서의 비관리 네이티브 Win32 코드에 대한 호출을 디버깅할 수 있습니다.|  
|**SQL Server 디버깅**|SQL Server 데이터베이스 개체를 디버깅할 수 있습니다.|  
|**Silverlight 디버깅**|Silverlight 구성 요소를 디버깅할 수 있습니다.|  
  
## <a name="see-also"></a>참고 항목  
 [디버거 설정 및 준비](../debugger/debugger-settings-and-preparation.md)