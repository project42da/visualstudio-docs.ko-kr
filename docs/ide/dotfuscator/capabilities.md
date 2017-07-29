---
title: "Dotfuscator의 기능 | Microsoft 문서"
ms.date: 2017-06-22
ms.prod: visual-studio-dev15
ms.devlang: dotnet
ms.technology:
- dotfuscator
ms.topic: article
keywords: "Dotfuscator, Dotfuscator CE, PreEmptive, PreEmptive Solutions, PreEmptive Protection, 보호, community edition, obfuscation, .NET, 무료, Visual Studio 2017"
helpviewer_keywords:
- PreEmptive Protection - Dotfuscator
- Dotfuscator Community Edition
- Dotfuscator CE
- Dotfuscator
- obfuscation
- protection
description: "Visual Studio 2017에 포함된 무료 Dotfuscator Community Edition의 기능을 알아봅니다."
ms.assetid: 0ee89c58-c900-48fc-a6a2-65ace00e8bab
author: Joe-Sewell-PreEmptive
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
ms.translationtype: Human Translation
ms.sourcegitcommit: 8ce85525f6af336682f6f8547c2f6c13dde73c8c
ms.openlocfilehash: 9193020b9031b5e1a5637fd4ec207d0449ec85ae
ms.contentlocale: ko-kr
ms.lasthandoff: 06/23/2017

---

# <a name="capabilities-of-dotfuscator"></a>Dotfuscator의 기능

이 페이지는 [업그레이드][upgrades]를 통해 사용 가능한 고급 옵션에 대한 몇몇 참조와 함께 Dotfuscator CE(Dotfuscator Community Edition)의 기능에 초점을 맞춥니다.

Dotfuscator는 .NET 응용 프로그램용 *빌드 후* 시스템입니다.
Dotfuscator CE를 통해 Visual Studio 사용자는 [어셈블리를 난독 처리][obfuscation]하고 [활성 방어][checks] 및 [분석 추적][analytics]을 응용 프로그램에 삽입할 수 있습니다. Dotfuscator가 없다면 모두 원래 소스 코드에 액세스해야 하는 작업입니다.
Dotfuscator는 계층화된 보호 전략을 생성하는 다양한 방법으로 응용 프로그램을 보호합니다.

Dotfuscator CE는 [UWP(유니버설 Windows 플랫폼)][uwp] 및 [Xamarin][xamarin]을 포함한 광범위한 .NET 어셈블리 및 응용 프로그램 형식을 지원합니다.

## <a name="intellectual-property-protection"></a>지적 재산권 보호

응용 프로그램의 디자인, 동작 및 구현은 IP(지적 재산권)의 형식입니다.
그러나 .NET Framework용으로 만들어진 응용 프로그램은 기본적으로 공개됩니다. [고급 메타데이터 및 중간 코드를 포함하므로 ][assemblies] .NET 어셈블리를 아주 쉽게 리버스 엔지니어링할 수 있습니다.

Dotfuscator CE에는 기본 [.NET 난독 처리][obfuscation]가 [이름 바꾸기][renaming] 형식으로 포함됩니다.
Dotfuscator를 통해 코드를 난독 처리하면 중요한 명명 정보가 더 이상 공개되지 않으므로 리버스 엔지이어링을 통해 소스 코드에 무단 액세스할 위험이 감소합니다.
난독 처리는 검사로부터 코드를 보호하려는 노력을 나타내며 IP를 거래 비밀로 법적으로 보호하도록 설정하는 중요한 단계입니다.

Dotfuscator CE의 다양한 [응용 프로그램 무결성 보호 기능](#application-integrity-protection)은 리버스 엔지니어링을 추가로 방지합니다.
예를 들어 잘못된 행위자가 프로그램 논리를 이해하기 위해 디버거를 응용 프로그램의 실행 중인 인스턴스에 연결하려고 시도할 수 있습니다.
Dotfuscator는 이 시도를 방지하기 위해 [디버그 방지 동작][debug]을 응용 프로그램에 삽입할 수 있습니다.

## <a name="application-integrity-protection"></a>응용 프로그램 무결성 보호

소스 코드 보호뿐 아니라 응용 프로그램이 설계된 대로 사용되도록 하는 것도 중요합니다.
공격자는 라이선싱 정책을 우회하거나(소프트웨어 불법 복제), 응용 프로그램에서 처리되는 중요한 데이터를 훔치거나 조작하거나, 응용 프로그램의 동작을 변경하기 위해 응용 프로그램을 하이재킹하려고 시도할 수 있습니다.

Dotfuscator CE는 [조작 방지][tamper] 및 [디버그 방지][debug] 대책을 포함하여 [응용 프로그램 유효성 검사 코드][checks]를 어셈블리에 삽입할 수 있습니다.
잘못된 응용 프로그램 상태가 검색되면 유효성 검사 코드가 [응용 프로그램 코드를 호출하여 상황을 적절한 방식으로 해결][check-app]할 수 있습니다.
또는 응용 프로그램의 잘못된 사용을 처리하는 코드를 작성하지 않으려는 경우 소스 코드를 수정할 필요 없이 Dotfuscator에서 [원격 분석 보고][check-telemetry] 및 [응답][check-action] 동작을 삽입할 수도 있습니다.

이와 같은 방법의 대부분은 평가 및 평가판 소프트웨어를 위해 [수명 종료 기한][shelflife]을 적용하는 데 사용될 수도 있습니다.

## <a name="application-monitoring"></a>응용 프로그램 모니터링

응용 프로그램을 개발할 경우 베타 테스터 및 이전 버전 사용자를 포함하여 사용자의 동작 패턴을 이해하는 것이 중요합니다.
응용 프로그램 분석을 통해 고객이 경험하는 오류를 포함하여 응용 프로그램이 얼마나 자주 사용되고 어떻게 사용되는지 추적할 수 있습니다.

Dotfuscator CE는 [예외 추적][exceptions], [세션 추적][sessions] 및 [기능 추적][features] 코드를 응용 프로그램에 삽입할 수 있습니다.
처리된 응용 프로그램은 실행 해 분석 데이터를 구성된 [PreEmptive Analytics 끝점][endpoints]에 전송합니다.

## <a name="see-also"></a>참고 항목

[전체 Dotfuscator CE 사용자 가이드의 이 항목][full]

<!-- Copyright © 2017 PreEmptive Solutions, LLC -->

[assemblies]: https://docs.microsoft.com/en-us/dotnet/standard/assembly-format
[uwp]: https://www.preemptive.com/blog/article/856-uwp-applications-in-dotfuscator-ce/91-dotfuscator-ce
[xamarin]: https://www.preemptive.com/obfuscating-xamarin-with-dotfuscator

[upgrades]: upgrades.md

[obfuscation]: https://www.preemptive.com/dotfuscator/ce/docs/help/obfuscation_overview.html
[renaming]: https://www.preemptive.com/dotfuscator/ce/docs/help/obfuscation_renaming.html

[analytics]: https://www.preemptive.com/dotfuscator/ce/docs/help/analytics_overview.html
[endpoints]: https://www.preemptive.com/dotfuscator/ce/docs/help/analytics_overview.html#endpoints

[checks]: https://www.preemptive.com/dotfuscator/ce/docs/help/checks_overview.html
[check-app]: https://www.preemptive.com/dotfuscator/ce/docs/help/checks_overview.html#app-notification
[check-action]: https://www.preemptive.com/dotfuscator/ce/docs/help/checks_overview.html#action

[tamper]: https://www.preemptive.com/dotfuscator/ce/docs/help/checks_tamper.html
[debug]: https://www.preemptive.com/dotfuscator/ce/docs/help/checks_debug.html
[shelflife]: https://www.preemptive.com/dotfuscator/ce/docs/help/checks_shelflife.html
[exceptions]: https://www.preemptive.com/dotfuscator/ce/docs/help/analytics_exceptions.html
[sessions]: https://www.preemptive.com/dotfuscator/ce/docs/help/analytics_sessions.html
[features]: https://www.preemptive.com/dotfuscator/ce/docs/help/analytics_features.html
[check-telemetry]: https://www.preemptive.com/dotfuscator/ce/docs/help/analytics_checks.html

[full]: https://www.preemptive.com/dotfuscator/ce/docs/help/intro_capabilities.html

