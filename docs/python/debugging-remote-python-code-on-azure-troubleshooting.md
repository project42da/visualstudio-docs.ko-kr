---
title: Python에 대한 Azure 원격 디버깅 문제 해결 | Microsoft Docs
description: Visual Studio를 사용하여 Azure App Service에서 실행 중인 Python 응용 프로그램을 디버그할 때 문제를 해결하는 방법입니다.
ms.custom: ''
ms.date: 07/12/2017
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-python
dev_langs:
- python
ms.tgt_pltfrm: ''
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: ghogen
ms.workload:
- python
- data-science
- azure
ms.openlocfilehash: 92429ea893c4eccee75f3a70ffda44eac8f91aa9
ms.sourcegitcommit: 29ef88fc7d1511f05e32e9c6e7433e184514330d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/28/2018
---
# <a name="remote-debugging-troubleshooter-for-python-and-azure"></a>Python 및 Azure에 대한 원격 디버깅 문제 해결사

다음 이유 중 하나로 Visual Studio에서 [원격 디버깅을 위해 Azure App Service](debugging-remote-python-code-on-azure.md)에 연결할 수 없습니다.

| 이유 | 해결 |
| --- | --- |
| Visual Studio 2013 업데이트 4 이상이 설치되어 있지 않습니다. | [visualstudio.com](https://www.visualstudio.com/downloads/)에서 적절한 버전을 설치합니다. | 
| App Service에 배포된 프로젝트가 Visual Studio에서 열리는 프로젝트와 일치하지 않습니다. | Visual Studio에 올바른 프로젝트를 로드합니다. |
| 프로젝트가 디버그 구성을 사용하여 배포되지 않았습니다. | [솔루션 탐색기]에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **게시**를 선택하여 응용 프로그램을 다시 배포합니다. **설정** 탭에서 **디버그**가 선택한 구성인지 확인합니다. |
| App Service가 실행되고 있지 않습니다. | Visual Studio의 [서버 탐색기] 또는 Azure Portal에서 시작합니다. |
| App Service가 웹 소켓에 대해 구성되어 있지 않습니다. | [Azure Portal](https://portal.azure.com), App Service로 차례로 이동하고, **설정 > 응용 프로그램 설정** 블레이드를 열어 **일반 설정 > 웹 소켓**을 **사용**으로 설정하고, **저장**을 선택합니다. (이 블레이드에 표시된 **디버깅** 옵션은 Python 디버깅에 *적용되지 않습니다*.) |
| `web.debug.config`에서 디버그 프록시를 사용하지 않도록 수정되었습니다. | 파일을 삭제하고 프로젝트를 App Service에 다시 게시합니다. 이 기간에 Visual Studio에서 파일을 다시 만듭니다. |

참고 항목:

- [Python에 대한 Azure 원격 디버깅](debugging-remote-python-code-on-azure.md)
