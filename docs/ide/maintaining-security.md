---
title: Visual Studio에서 응용 프로그램 보안 유지 관리
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- unauthorized access
- Baseline Security Analyzer
- Microsoft Baseline Security Analyzer
- security [.NET Framework], best practices
- MBSA (Microsoft Baseline Security Analyzer)
- security [.NET Framework], maintaining after deployment
ms.assetid: 621d10c1-842b-4902-be60-bb9719591751
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ee7a90804c2161fe927bebc2b2f1af45862b8ccd
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="maintain-security"></a>보안 유지

지속적인 경계가 보안의 대가라는 말이 있습니다. 응용 프로그램을 디자인하고 개발하는 동안 보안 문제에 최대한 신경을 많이 써도 배포 후에 보안 결함이 나타날 수 있습니다. 응용 프로그램을 감사하고 이벤트 로그를 분석하면 이전에 몰랐던 결함을 발견할 수도 있습니다.

또한 응용 프로그램에 대한 경계를 늦추지 않아야 할 뿐만 아니라 응용 프로그램이 실행되는 플랫폼과 종속되는 다른 제품의 보안 위협 및 결함을 지속적으로 확인해야 합니다.

[보안, 개인 정보 및 계정](https://support.microsoft.com/products/microsoft-account?category=privacy#security-privacy-accounts-help=windows-8&v0h=winrttab1&v1h=win8tab1&v2h=win7tab1&v3h=winvistatab1)&mdash;바이러스, 암호, 자녀 보호, 방화벽 및 드라이브 암호화에 대한 정보를 비롯하여 보안, 개인 정보 및 사용자 계정에 대한 도움을 받아 보십시오.

[Microsoft 보안 업데이트 게시판](https://technet.microsoft.com/security/bulletins.aspx)&mdash;이 페이지는 이전에 릴리스된 게시판을 쉽게 찾을 수 있도록 구성되어 있습니다. IT 전문가를 위한 보안 게시판에는 보안 업데이트와 관련된 자세한 정보가 있습니다.

[MBSA(Microsoft Baseline Security Analyzer)](https://www.microsoft.com/download/details.aspx?id=7558)&mdash;MBSA는 가정이나 회사의 개인 사용자 또는 관리자가 한 대 이상의 Windows 기반 컴퓨터에서 일반적인 보안 구성 실수를 검색할 수 있는 도구입니다.