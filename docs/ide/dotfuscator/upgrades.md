---
title: "Dotfuscator CE(Community Edition) 업그레이드 | Microsoft 문서"
ms.date: 2017-02-08
ms.prod: visual-studio-dev15
ms.devlang: dotnet
ms.technology:
- dotfuscator
ms.topic: article
keywords: "Dotfuscator, Dotfuscator CE, PreEmptive, PreEmptive Solutions, PreEmptive Protection, 보호, community edition, obfuscation, .NET, 무료, Visual Studio 2017, 업그레이드, 명령줄"
helpviewer_keywords:
- PreEmptive Protection - Dotfuscator
- Dotfuscator Community Edition
- Dotfuscator CE
- Dotfuscator
- obfuscation
- protection
- Dotfuscator upgrade
- upgrade Dotfuscator
- upgrading Dotfuscator
- register Dotfuscator
- registering Dotfuscator
- Dotfuscator command line
- Dotfuscator Professional
description: "Visual Studio 2017에 포함된 무료 Dotfuscator Community Edition을 업그레이드하는 방법을 알아봅니다."
ms.assetid: c7c60904-27f9-4f1f-b79b-ddf65041b810
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
ms.openlocfilehash: 60ca38639f6523cdbace4efa4aa48b48d5e9a886
ms.contentlocale: ko-kr
ms.lasthandoff: 06/23/2017

---

# Dotfuscator CE(Community Edition) 업그레이드
<a id="upgrade-dotfuscator-community-edition-ce" class="xliff"></a>

Dotfuscator CE(Dotfuscator Community Edition)는 Microsoft Visual Studio를 사용하는 모든 개발자에게 즉시 다양한 응용 프로그램 보호 및 강화 기능을 제공합니다.
그러나 Dotfuscator 버전을 업그레이드하는 사용자에게는 더 많은 기능이 제공됩니다.

## Dotfuscator CE 등록
<a id="registering-dotfuscator-ce" class="xliff"></a>

Dotfuscator CE의 등록된 사용자는 [명령줄 지원][cli]과 같은 추가 기능에 액세스할 수 있어 Dotfuscator CE를 자동화된 빌드 프로세스에 쉽게 통합할 수 있습니다.

등록은 빠르고 간단하며 무료입니다.
Dotfuscator CE를 등록하려면 [전체 Dotfuscator CE 사용자 가이드의 Getting Started(시작) 페이지에 있는 Registering Dotfuscator CE(Dotfuscator CE 등록) 섹션][register-ce]을 참조하세요.

## Dotfuscator Professional
<a id="dotfuscator-professional" class="xliff"></a>

Dotfuscator Community Edition은 기본적인 보호를 제공하지만 **_PreEmptive Protection - Dotfuscator_ Professional Edition**에는 향상된 난독 변환 및 보호 기능이 포함됩니다.
여기에는 다음이 포함됩니다.

* *지적 재산권 보호*
  * Enhanced Overload Induction™ 및 임의 식별자 선택을 포함한 추가적인 이름 바꾸기 옵션.
  * 난독 처리된 스택 추적을 디코딩하기 위한 도구.
  * [자동화된 코드 디컴파일을 방지하기 위한 변환][control-flow]을 포함하여 엔터프라이즈급 난독 변환에 액세스.
  * 디컴파일된 코드를 단순 검색하지 못하도록 [중요한 문자열을 가리는][string-encryption] 기능.
  * 권한이 없는 소프트웨어 누수의 원인을 파악할 수 있도록 [소유권 및 배포 문자열을 어셈블리에 신중하게 포함][watermarking](소프트웨어 워터마크 처리)하는 기능.
  * 중요한 부분이 분리되지 않아 공격자가 코드 요소의 역할을 확인하기가 훨씬 더 어렵도록 [어셈블리 여러 개를 하나로 결합][linking]하는 기능.
  * 전달되는 중요한 코드의 양을 줄이도록 [자동으로 응용 프로그램에서 사용되지 않는 코드를 제거][pruning]하는 기능.
* *응용 프로그램 무결성 보호*
  * 추가적인 [응용 프로그램 방어 동작][check-actions].
  * 조작 방지 및 디버그 방지 코드를 `.dll` 어셈블리에 삽입하는 기능.
  * 응용 프로그램의 수명 종료 기한 전에 경고 기간을 제공하는 기능.
  * 수명 종료 경고 기간 중에 또는 기한 후에 응용 프로그램 코드를 알리는 기능.
  * 원격 분석 암호화.
* *응용 프로그램 모니터링*
  * 일시적인 네트워크 장애 중에 수집된 정보를 수집 및 저장하는 기능.
  * 개인 식별 정보를 수집하는 기능.
  * [기능 추적][features] 무제한 사용.
  * 처리되지 않은 예외 이외에 코드로 catch 및 throw된 예외를 추적하는 기능.
  * `.dll` 어셈블리에서 예외를 추적하는 기능.
  * 원격 분석 암호화.

Dotfuscator Professional은 산업 표준 [.NET Obfuscator][net-obfuscator]이고 지속적인 지원, 유지 관리 및 제품 업데이트가 필요한 엔터프라이즈 개발자에게 적합합니다.
또한 Dotfuscator Professional은 Visual Studio와 더 밀접하게 통합되고 상업적으로 사용이 허가됩니다.

Dotfuscator Professional의 고급 응용 프로그램 보호 기능에 대한 자세한 내용은 PreEmptive Solutions의 [Dotfuscator Overview(Dotfuscator 개요) 페이지][product-about]를 방문해서 [Community Edition과 비교][product-compare]해 보세요.
[preemptive.com][eval]에서 요청 시 전체 기능이 지원되는 평가판을 사용할 수 있습니다.

## 참고 항목
<a id="see-also" class="xliff"></a>

[전체 Dotfuscator CE 사용자 가이드의 이 항목][full]

<!-- Copyright © 2017 PreEmptive Solutions, LLC -->

[control-flow]: https://www.preemptive.com/products/dotfuscator/features#controlflow
[string-encryption]: https://www.preemptive.com/products/dotfuscator/features#string
[watermarking]: https://www.preemptive.com/products/dotfuscator/features#watermarking
[linking]: https://www.preemptive.com/products/dotfuscator/features#linking
[pruning]: https://www.preemptive.com/products/dotfuscator/features#pruning

[check-actions]: https://www.preemptive.com/images/stories/Dotfuscator/webframe.html#Check%20Actions.html
[features]: https://www.preemptive.com/images/stories/Dotfuscator/webframe.html#Feature_Usage_Tracking_and_the_Feature_Attribute.html

[net-obfuscator]: https://www.preemptive.com/products/dotfuscator/overview
[eval]: https://www.preemptive.com/eval-request

[product-about]: https://www.preemptive.com/products/dotfuscator/overview
[product-compare]: https://www.preemptive.com/products/dotfuscator/compare-editions

[cli]: https://www.preemptive.com/dotfuscator/ce/docs/help/intro_cli.html
[register-ce]: https://www.preemptive.com/dotfuscator/ce/docs/help/gui_getstarted.html#register

[full]: https://www.preemptive.com/dotfuscator/ce/docs/help/intro_upgrades.html

