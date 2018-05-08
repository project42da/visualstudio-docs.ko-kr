---
title: Dotfuscator CE(Community Edition)
ms.date: 10/10/2017
ms.devlang: dotnet
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
keywords: Dotfuscator, Dotfuscator CE, PreEmptive, PreEmptive Solutions, PreEmptive Protection, 보호, community edition, obfuscation, .NET, 무료, Visual Studio 2017
helpviewer_keywords:
- PreEmptive Protection Dotfuscator
- Dotfuscator Community Edition
- Dotfuscator CE
- Dotfuscator
- obfuscation
- protection
description: Visual Studio 2017에 포함된 무료 Dotfuscator Community Edition으로 .NET 응용 프로그램을 보호하는 방법에 대해 알아봅니다.
ms.assetid: d9550502-0a82-49a6-b005-2caa791fbe02
author: Joe-Sewell-PreEmptive
ms.author: gewarren
manager: douge
ms.openlocfilehash: a81d640e2ecebe46a20f7a3661584cb5c7423691
ms.sourcegitcommit: 56018fb1f52f17bf35ae2ce71c50c763486e6173
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="dotfuscator-community-edition-ce"></a>Dotfuscator CE(Community Edition)

*PreEmptive Protection - Dotfuscator*는 보안 소프트웨어 개발 수명 주기에 맞도록 손쉽게 조정되는 포괄적인 .NET 응용 프로그램 보호 기능을 제공합니다.
이 프로그램을 사용하여 데스크톱, 모바일, 서버 및 포함된 응용 프로그램을 강화, 보호 및 정리함으로써 거래 비밀 및 기타 IP(지적 재산권)를 보호하고, 불법 복제 및 위조를 줄이고, 변조 및 무단 디버깅으로부터 보호하는 데 도움을 얻을 수 있습니다.
Dotfuscator는 추가적인 프로그래밍이나 소스 코드 액세스 없이도 컴파일된 어셈블리에 작동합니다.

![PreEmptive Protection - Dotfuscator](media/header.svg)

## <a name="why-protection-matters"></a>보호가 중요한 이유

**IP(지적 재산권)을 보호**하는 일은 매우 중요합니다.
응용 프로그램의 코드에는 IP로 간주할 수 있는 디자인 및 구현 세부 정보가 포함되어 있습니다.
그렇지만 .NET Framework에서 빌드된 응용 프로그램에는 [중요한 메타데이터 및 고급 중간 코드][assemblies]가 포함되어 있으며 이러한 항목들은 수많은 무료 자동화 도구 중 하나만으로 쉽게 리버스 엔지니어링할 수 있습니다.
리버스 엔지니어링을 중단하고 중지하여 무단 IP 공개를 방지하고 코드에 영업 비밀이 포함되어 있음을 알릴 수 있습니다.
Dotfuscator는 원래 응용 프로그램 동작은 유지하면서 .NET 어셈블리를 [난독 처리][obfuscation]하여 리버스 엔지니어링을 방지할 수 있습니다.

**응용 프로그램의 무결성을 보호**하는 것도 중요합니다.
리버스 엔지니어링 외에도 악의적인 사용자가 응용 프로그램을 불법 복제하거나, 런타임에 응용 프로그램의 동작을 변경하거나, 데이터를 조작하려고 할 수 있습니다.
Dotfuscator는 응용 프로그램에 변조 및 제3자 디버깅을 비롯한 [무단 사용을 감지, 보고 및 반응][checks]하는 기능을 주입합니다.

Dotfuscator를 보안 소프트웨어 개발 수명 주기에 적용하는 방법에 대한 자세한 내용은 PreEmptive Solutions의 [SDL 응용 프로그램 보호 페이지][sdl-protection]를 참조하세요.

## <a name="about-dotfuscator-ce"></a>Dotfuscator CE 정보

Microsoft Visual Studio 2017의 복사본에는 Dotfuscator CE로도 알려진 ***PreEmptive Protection - Dotfuscator* Community Edition**의 복사본이 있으며, 개인 용도로 사용 시 무료로 제공됩니다.
Visual Studio 2017에 포함된 Dotfuscator CE 버전을 설치하는 방법에 대한 지침은 [설치 페이지][install]를 참조하세요.

Dotfuscator CE는 개발자, 설계자 및 테스터를 위한 광범위한 [소프트웨어 보호 및 보안 강화][software-protection] 서비스를 제공합니다.
Dotfuscator CE에 포함된 [.NET Obfuscation][obfuscation] 및 기타 [응용 프로그램 보호] [app-protection] 기능의 예는 다음과 같습니다.

* 식별자 *[이름 바꾸기][renaming]*  - 컴파일된 어셈블리의 리버스 엔지니어링을 더 어렵게 만듭니다.
* *[변조 방지][tamper]*  - 변조된 응용 프로그램의 실행을 감지하고, 인시던트 경고를 전송하고, 변조된 세션을 종료합니다.
* *[디버그 방지][debug]*  - 실행 중인 응용 프로그램에 대한 디버거 연결을 감지하고, 인시던트 경고를 전송하고, 디버그된 세션을 종료합니다.
* *[응용 프로그램 만료 동작][shelflife]* - “수명 종료" 날짜를 인코딩하고, 만료 날짜 이후에 응용 프로그램이 실행될 경우 경고를 전송하고, 만료된 응용 프로그램 세션을 종료합니다.
* *[예외 추적][exceptions]*  - 응용 프로그램 내에서 발생하는 처리되지 않은 예외를 모니터링합니다.
* *[세션][sessions] 및 [기능][features] 사용 추적* - 실행된 응용 프로그램, 이러한 응용 프로그램의 버전 및 해당 응용 프로그램에서 사용된 기능을 확인합니다.

이러한 기능과 이러한 기능이 응용 프로그램 보호 전략에 맞게 조정되는 방법에 대한 자세한 내용은 [기능 페이지][capabilities]를 참조하세요.

Dotfuscator CE는 통합된 기본 보호 기능을 제공합니다.
Dotfuscator CE에 등록한 사용자와 전 세계에서 널리 사용되고 있는 [.NET Obfuscator][net-obfuscator]인 *PreEmptive Protection - Dotfuscator* Professional Edition 사용자는 더 많은 응용 프로그램 보호 기능을 사용할 수 있습니다.
Dotfuscator를 강화하는 방법에 대한 자세한 내용은 [업그레이드 페이지][upgrades]를 참조하세요.

## <a name="getting-started"></a>시작

Visual Studio에서 Dotfuscator CE 사용을 시작하려면 **빠른 실행**(Ctrl + Q) 검색 창에 `dotfuscator`를 입력합니다.

* Dotfuscator CE가 이미 설치되어 있으면 **빠른 실행**이 Dotfuscator CE 사용자 인터페이스를 시작하는 *메뉴* 옵션을 표시합니다. 자세한 내용은 [전체 Dotfuscator CE 사용자 가이드의 시작 페이지][get-started]를 참조하세요.
* Dotfuscator CE가 아직 설치되어 있지 않은 경우 **빠른 실행**이 관련 *설치* 옵션을 표시합니다. 자세한 내용은 [설치 페이지][install]를 참조하세요.

[preemptive.com의 Dotfuscator 다운로드 페이지][download]에서 **최신 버전**을 불러올 수도 있습니다.

## <a name="full-documentation"></a>전체 설명서

이 페이지와 해당 하위 페이지에는 Dotfuscator CE 기능에 대한 자세한 개요와 [도구 설치 지침][install]이 제공되어 있습니다.

[Dotfuscator CE 사용자 인터페이스 사용을 시작하는 방법][get-started]을 비롯한 자세한 사용 지침은 [preemptive.com의 전체 Dotfuscator CE 사용자 가이드][full]를 참조하세요.

<!-- Copyright © 2017 PreEmptive Solutions, LLC -->

- [assemblies]: https://docs.microsoft.com/en-us/dotnet/standard/assembly-format
- [software-protection]: https://www.preemptive.com/software-protection
- [obfuscation]: https://www.preemptive.com/obfuscation
- [app-protection]: https://www.preemptive.com/application-protection
- [sdl-protection]: https://www.preemptive.com/solutions/SDL-App-Protection
- [net-obfuscator]: https://www.preemptive.com/products/dotfuscator/overview
- [download]: https://www.preemptive.com/products/dotfuscator/downloads

- [install]: install.md
- [capabilities]: capabilities.md
- [upgrades]: upgrades.md

- [get-started]: https://www.preemptive.com/dotfuscator/ce/docs/help/gui_getstarted.html

- [renaming]: https://www.preemptive.com/dotfuscator/ce/docs/help/obfuscation_renaming.html

- [checks]: https://www.preemptive.com/dotfuscator/ce/docs/help/checks_overview.html
- [tamper]: https://www.preemptive.com/dotfuscator/ce/docs/help/checks_tamper.html
- [debug]: https://www.preemptive.com/dotfuscator/ce/docs/help/checks_debug.html
- [shelflife]: https://www.preemptive.com/dotfuscator/ce/docs/help/checks_shelflife.html

- [exceptions]: https://www.preemptive.com/dotfuscator/ce/docs/help/instrumentation_exceptions.html
- [sessions]: https://www.preemptive.com/dotfuscator/ce/docs/help/instrumentation_sessions.html
- [features]: https://www.preemptive.com/dotfuscator/ce/docs/help/instrumentation_features.html

- [full]: https://www.preemptive.com/dotfuscator/ce/docs/help/index.html