---
title: IntelliCode FAQ
ms.date: 05/07/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
manager: douge
author: markw-t
ms.author: mwthomas
ms.openlocfilehash: df5ce60e9d7a05d8cc7c9ebbe173dd30a0a0edf4
ms.sourcegitcommit: eefffa7ebe339d1297cdc12f51a813e7849d7e95
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2018
---
# Visual Studio IntelliCode FAQ

Visual Studio IntelliCode에 관심을 가져 주셔서 감사합니다. 귀하가 궁금해 할 만한 몇 가지 사항에 해답이 되기를 바라면서 간단한 FAQ를 준비했습니다.

## 질문. Visual Studio IntelliCode란 무엇인가요?

빌드 2018에는 AI를 사용하여 소프트웨어 개발을 개선하는 새로운 기능인 Visual Studio IntelliCode가 도입되었습니다. IntelliCode는 개발자와 팀이 자신 있게 코딩하고, 더 빠르게 문제를 찾고, 코드 검토에 집중하는 데 도움을 줍니다.

다음과 같은 방법으로 IntelliCode가 소프트웨어 개발 프로세스를 개선 하는 방법의 초기 모습을 보여 드렸습니다.

- 컨텍스트 인식 코드 완성본 제공
- 개발자에게 팀의 패턴 및 스타일을 준수하도록 안내
- 찾기 어려운 코드 문제 발견
- 정말 중요한 영역으로 주의를 끌어 코드 검토에 집중

개발자는 [https://aka.ms/intellicode](https://aka.ms/intellicode)에서 자세한 정보를 찾고 새로운 소식 및 향후 비공개 미리 보기를 위해 등록할 수 있습니다.

## 질문. 고객은 Visual Studio IntelliCode로 무엇을 할 수 있나요?

Visual Studio IntelliCode는 AI(인공 지능)를 통해 새로운 생산성 향상 기능을 제공하는 광범위한 기능입니다.

개발자는 Visual Studio 2017 버전 15.7 이상을 위한 [실험적 확장을 다운로드](https://go.microsoft.com/fwlink/?linkid=872707)할 수 있습니다. 이 확장은 멤버에 대한 사전순 목록만 제공하지 않고 개발자가 사용하기에 가장 적합한 API를 예측하는 향상된 IntelliSense를 제공합니다. 개발자의 현재 코드 컨텍스트 및 패턴을 사용하여 이 동적 목록을 제공합니다. 몇 달 내로 확장에 추가 기능을 업데이트할 예정입니다.

## Q: IntelliCode에서 제공하는 “AI 지원 IntelliSense”가 일반 IntelliSense보다 나은 이유는 무엇인가요?

IntelliCode의 완성 목록은 단순한 사전순 멤버 목록을 제공하는 것이 아니라 개발자가 사용하기에 가장 적합한 API를 제안합니다. 개발자의 현재 코드 컨텍스트와 각각 100개 이상의 별점이 달린 GitHub의 고품질 오픈 소스 프로젝트 2000개에 기반을 둔 패턴을 사용하여 이러한 동적 목록을 제공합니다. 그 결과 가능성과 관련성이 가장 높은 API 호출을 예측하는 모델이 형성됩니다.

## Q: IntelliCode 완성 제안 기능은 얼마나 유용한가요?

Microsoft 내부에서 IntelliCode의 추천 기능을 얼마 동안 사용해 보았는데 유용한 제안 기능인 것 같습니다. 하지만 결국 직접 코딩할 때 이러한 추천 기능이 얼마나 유용한지 알 수 있을 것입니다. Visual Studio [IntelliCode 확장](https://go.microsoft.com/fwlink/?linkid=872707)을 한번 사용해 보시기 바랍니다. 얼마나 유용했는지 알려주시고, 피드백을 보내주세요. 또한 여러분이 추천 기능 중에서 선택한 항목에 따라 모델을 학습시켜 모델을 개선하면서 확장을 업데이트할 것입니다.

> [!NOTE]
> 사용자 정의 코드는 수집되지 않습니다. [개인 정보 보호](#privacy)에 대한 질문을 참조하세요.

## 질문. IntelliCode는 미래에 어떻게 되나요?

AI 및 기타 고급 기술을 사용하여 개발자의 생산성을 개선하기 위한 다양한 방법을 연구하는 중입니다. 빌드 2018에서는 AI가 개발자에게 도움이 될 만한 몇 가지 시나리오의 초기 모습을 보여 주었지만 그 밖에도 많이 있습니다. 지금까지 당사에서 보여 드린 기능을 가지고 실험하는 개발자 분들의 의견을 듣고 싶습니다. [https://aka.ms/intellicode](https://aka.ms/intellicode)에서 가입하여 뉴스 및 업데이트를 받아보세요.

## 질문. 가격은 얼마인가요?

현재 가격 책정과 관련한 공지 사항은 없습니다.

## 질문. IntelliCode는 언제 출시되나요?

IntelliCode의 AI 지원 IntelliSense는 현재 첫 번째 실험적 미리 보기 상태입니다. 실험적 확장을 계속 업데이트하고, 향후 기능을 추가할 예정입니다. 최종 릴리스 날짜는 아직 미정이지만 최상의 경험을 제공하기 위해 개발자 여러분들의 피드백을 기다립니다. [https://aka.ms/intellicode](https://aka.ms/intellicode)에서 가입하여 뉴스 및 업데이트를 받아볼 수 있습니다.

## 질문. 이 환경은 Visual Studio 및 C#에서만 사용할 수 있나요?

이 환경은 C# 코드베이스의 Visual Studio 2017 빌드 2018에 도입되었습니다. 하지만 향후 Visual Studio 제품군의 더 많은 언어와 도구로 IntelliCode를 확장할 예정입니다.

## 질문. 이 확장을 실행하는 데 필요한 Visual Studio 릴리스는 무엇인가요?

Visual Studio IntelliCode 확장은 Visual Studio 2017 버전 15.7 미리 보기 5 이상(모든 SKU)에서 지원됩니다. 필요한 최소 버전이 설치되지 않은 경우 "이 확장은 현재 설치되어 있는 제품에 설치할 수 없습니다."와 함께 확장 설치가 중단됩니다.

## 질문. 이 환경은 영어로만 지원되나요?

IntelliCode는 현재 미리 보기 확장이며, Microsoft에서는 이러한 기능이 광범위한 고객에게 얼마나 유용한지 파악하고자 합니다. IntelliCode 미리 보기가 종료되면 여러분의 피드백에 따라 우선적으로 지원할 로캘이나 언어, 패키징 방법을 확실히 고려할 것입니다. 

## <a name="privacy"/> Q: 개인 정보 보호는 어떤가요? 제 코드가 클라우드로 전송되나요? 어떤 고객 데이터가 Microsoft로 전송되나요?

개발자 여러분, 지금 바로 실험적 미리 보기 확장인 Visual Studio IntelliCode를 사용해 보시기 바랍니다. 이 확장의 목적은 개발자 여러분들이 IntelliCode의 기능을 테스트하고 제품 팀에 의견을 제공하도록 하는 것입니다.

제품 개선을 위해 확장에서 익명화된 사용 및 오류 보고 데이터 중 일부가 수집됩니다. 사용자 정의 코드는 Microsoft로 전송되지 않지만 IntelliCode 결과 사용에 대한 정보는 수집됩니다. 이 데이터에는 오픈 소스 및 .NET 형식과 개발자가 IntelliCode의 제안 목록에서 선택한 멤버만 포함됩니다. 개발자는 Visual Studio 데이터 수집을 옵트아웃할 수 있으며, 그러면 IntelliCode 확장에 대한 데이터 수집도 해제됩니다. 메뉴 표시줄에서 **도움말** > **의견 보내기** > **설정**을 선택합니다. **Visual Studio 환경 개선 프로그램** 대화 상자에서 **아니요, 참여하지 않겠습니다**를 선택한 후 **확인**을 선택합니다.

IntelliCode 확장은 정기적으로 개발자에게 설문 조사를 완료하도록 요청할 수 있습니다. 다시 말하지만 이 설문 조사는 익명으로 처리됩니다. 사용자는 가입하여 뉴스 및 이후 비공개 미리 보기를 받아볼 수 있지만 현재 실험적 확장을 사용할 때는 그렇게 하지 않아도 됩니다.

향후 기능에서는 가입이 필요한 서비스에 대한 액세스 권한을 요청할 수 있습니다. 이러한 기능의 비공개 미리 보기가 준비되면 자세한 내용을 알려드리겠습니다.
