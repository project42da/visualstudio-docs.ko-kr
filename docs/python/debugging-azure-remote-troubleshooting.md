---
title: "Visual Studio용 Python 도구를 사용하여 Azure 원격 디버깅 문제 해결 | Microsoft Docs"
ms.custom: 
ms.date: 3/7/2017
ms.prod: visual-studio-dev15
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-python
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b723b343-dffb-457e-9af7-ee48c1451e30
caps.latest.revision: 1
author: kraigb
ms.author: kraigb
manager: ghogen
translation.priority.ht:
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
translationtype: Human Translation
ms.sourcegitcommit: a42f5a30375192c89c9984e40ba0104da98d7253
ms.openlocfilehash: fcf44a3967c0bd391808c9f6b3a23f39aeff05fd
ms.lasthandoff: 03/07/2017

---

# <a name="remote-debugging-troubleshooter-for-python-and-azure"></a>Python 및 Azure에 대한 원격 디버깅 문제 해결사

다음 이유 중 하나로 Visual Studio에서 [원격 디버깅을 위해 Azure App Service](debugging-azure-remote.md)에 연결할 수 없습니다.

| 이유 | 해결 |
| --- | --- |
| Visual Studio 2013 업데이트 4 이상이 설치되어 있지 않습니다. | [visualstudio.com](https://www.visualstudio.com/downloads/)에서 적절한 버전을 설치합니다. | 
| App Service에 배포된 프로젝트가 Visual Studio에서 열리는 프로젝트와 일치하지 않습니다. | Visual Studio에 올바른 프로젝트를 로드합니다. |
| 프로젝트가 디버그 구성을 사용하여 배포되지 않았습니다. | [솔루션 탐색기]에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **게시**를 선택하여 응용 프로그램을 다시 배포합니다. **설정** 탭에서 **디버그**가 선택한 구성인지 확인합니다. |
| App Service가 실행되고 있지 않습니다. | Visual Studio의 [서버 탐색기] 또는 Azure Portal에서 시작합니다. |
| App Service가 웹 소켓에 대해 구성되어 있지 않습니다. | [Azure Portal](https://portal.azure.com), App Service로 차례로 이동하고, **설정 > 응용 프로그램 설정** 블레이드를 열어 **일반 설정 > 웹 소켓**을 **사용**으로 설정하고, **저장**을 선택합니다. (이 블레이드에 표시된 **디버깅** 옵션은 Python 디버깅에 *적용되지 않습니다*.) |
| `web.debug.config`에서 디버그 프록시를 사용하지 않도록 수정되었습니다. | 파일을 삭제하고 프로젝트를 App Service에 다시 게시합니다. 이 기간 동안 Visual Studio용 Python 도구에서 파일을 다시 만듭니다. |

참고 항목:

- [Python에 대한 Azure 원격 디버깅](debugging-azure-remote.md)

