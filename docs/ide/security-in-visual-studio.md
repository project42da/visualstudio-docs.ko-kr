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
translationtype: Human Translation
ms.sourcegitcommit: ca7c86466fa23fb21a932f26dc24e37c71cf29b4
ms.openlocfilehash: 57f7d51786d2636eb865eb81bb3468e79c6f19f9
ms.lasthandoff: 04/05/2017

---
# <a name="security-in-visual-studio"></a>Visual Studio의 보안
디자인에서 배포에 이르기까지 응용 프로그램을 개발하는 모든 과정에 보안을 고려해야 합니다. Visual Studio를 최대한 안전하게 실행하여 시작합니다. [사용자 권한](../ide/user-permissions-and-visual-studio.md)을 참조하세요.  
  
 안전한 응용 프로그램을 효과적으로 개발하려면 보안 개념 및 개발할 플랫폼의 보안 기능에 대한 기본적인 내용과 보안 코딩 기술을 이해하고 있어야 합니다.  
  
## <a name="understanding-security"></a>보안 이해  
 [보안](http://msdn.microsoft.com/Library/9a9621d7-8883-4a4f-a874-65e8e09e20a6)  
 .NET Framework 코드 액세스 보안, 역할 기반 보안, 보안 정책 및 보안 도구에 대해 설명합니다.  
  
 [Defend Your Code with Top Ten Security Tips Every Developer Must Know](http://go.microsoft.com/fwlink/?LinkId=72877)(모든 개발자가 알아야 할 10가지 보안 팁으로 코드 보호하기)  
 데이터나 시스템이 손상되지 않도록 감시해야 하는 문제에 대해 설명합니다.  
  
## <a name="coding-for-security"></a>보안 코딩  
 보안 문제를 일으키는 대부분의 코딩 오류는 개발자가 사용자 입력에 대해 잘못 가정하거나 개발 중인 플랫폼을 완전히 이해하지 못하기 때문에 발생합니다.  
  
 [보안 코딩 지침](http://msdn.microsoft.com/Library/4f882d94-262b-4494-b0a6-ba9ba1f5f177)  
 보안 문제를 해결하기 위해 구성 요소를 분류하는 데 필요한 지침을 제공합니다.  
  
 [보안 모범 사례](/cpp/top/security-best-practices-for-cpp)  
 /GS 컴파일 시간 플래그에서 제공하는 Microsoft Visual C++ 보안 검사 기능의 전체 개요 및 버퍼 오버런에 대해 설명합니다.

## <a name="building-for-security"></a>보안에 대해 빌드  
 보안 또한 빌드 프로세스에서 중요한 고려 사항입니다.  몇 가지 추가 단계로 배포된 앱의 보안을 향상하고 무단 리버스 엔지니어링, 스푸핑 또는 기타 공격을 방지할 수 있습니다.

 [Dotfuscator CE(Community Edition)](dotfuscator/index.md)  
 무료 PreEmptive Protection - Dotfuscator Community Edition을 설정하고 시작하여 리버스 엔지니어링 및 무단 사용(무단 디버깅 등)으로부터 .NET 어셈블리를 보호하는 방법을 설명합니다.
  
 [어셈블리 및 매니페스트 서명 관리](managing-assembly-and-manifest-signing.md)  
 이름 스푸핑을 방지하기 위해, 소프트웨어 구성 요소를 고유하게 식별하는 데 사용할 수 있는 강력한 이름 서명에 관해 설명합니다.
