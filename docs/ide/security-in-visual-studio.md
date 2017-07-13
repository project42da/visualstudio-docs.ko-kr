---
title: "Visual Studio의 보안 | Microsoft 문서"
ms.custom: 
ms.date: 02/17/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- code access security, coding errors
- security [.NET Framework], about security
ms.assetid: 318c34ce-f643-468c-83a1-843196f5d845
caps.latest.revision: 20
author: kempb
ms.author: kempb
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
ms.sourcegitcommit: 3d32d11a430227800cb3ed53831a9565eb6adeb3
ms.openlocfilehash: 7314921a9416184c4bd63312bd5a82cef4102ddd
ms.contentlocale: ko-kr
ms.lasthandoff: 05/30/2017

---
# Visual Studio의 보안
<a id="security-in-visual-studio" class="xliff"></a>
디자인에서 배포에 이르기까지 응용 프로그램을 개발하는 모든 과정에 보안을 고려해야 합니다. Visual Studio를 최대한 안전하게 실행하여 시작합니다. [사용자 권한](../ide/user-permissions-and-visual-studio.md)을 참조하세요.  
  
 안전한 응용 프로그램을 효과적으로 개발하려면 보안 개념 및 개발할 플랫폼의 보안 기능에 대한 기본적인 내용과 보안 코딩 기술을 이해하고 있어야 합니다.  
  
## 보안 이해
<a id="understanding-security" class="xliff"></a>  
 [보안](/dotnet/standard/security/index)  
 .NET Framework 코드 액세스 보안, 역할 기반 보안, 보안 정책 및 보안 도구에 대해 설명합니다.  
  
 [Defend Your Code with Top Ten Security Tips Every Developer Must Know](http://go.microsoft.com/fwlink/?LinkId=72877)(모든 개발자가 알아야 할 10가지 보안 팁으로 코드 보호하기)  
 데이터나 시스템이 손상되지 않도록 감시해야 하는 문제에 대해 설명합니다.  
  
## 보안 코딩
<a id="coding-for-security" class="xliff"></a>  
 보안 문제를 일으키는 대부분의 코딩 오류는 개발자가 사용자 입력에 대해 잘못 가정하거나 개발 중인 플랫폼을 완전히 이해하지 못하기 때문에 발생합니다.  
  
 [보안 코딩 지침](/dotnet/standard/security/secure-coding-guidelines)  
 보안 문제를 해결하기 위해 구성 요소를 분류하는 데 필요한 지침을 제공합니다.  
  
 [보안 모범 사례](/cpp/top/security-best-practices-for-cpp)  
 /GS 컴파일 시간 플래그에서 제공하는 Microsoft Visual C++ 보안 검사 기능의 전체 개요 및 버퍼 오버런에 대해 설명합니다.

## 보안에 대해 빌드
<a id="building-for-security" class="xliff"></a>  
 보안 또한 빌드 프로세스에서 중요한 고려 사항입니다.  몇 가지 추가 단계로 배포된 앱의 보안을 향상하고 무단 리버스 엔지니어링, 스푸핑 또는 기타 공격을 방지할 수 있습니다.

 [Dotfuscator CE(Community Edition)](dotfuscator/index.md)  
 무료 PreEmptive Protection - Dotfuscator Community Edition을 설정하고 시작하여 리버스 엔지니어링 및 무단 사용(무단 디버깅 등)으로부터 .NET 어셈블리를 보호하는 방법을 설명합니다.
  
 [어셈블리 및 매니페스트 서명 관리](managing-assembly-and-manifest-signing.md)  
 이름 스푸핑을 방지하기 위해, 소프트웨어 구성 요소를 고유하게 식별하는 데 사용할 수 있는 강력한 이름 서명에 관해 설명합니다.
