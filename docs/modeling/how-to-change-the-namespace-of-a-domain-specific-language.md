---
title: '방법: 도메인별 언어의 네임스페이스 변경'
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Domain-Specific Language, namespace
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: 1963502f3940fd0d17c770f111e07de14207e687
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-change-the-namespace-of-a-domain-specific-language"></a>방법: 도메인별 언어의 네임스페이스 변경
도메인 특정 언어의 네임 스페이스를 변경할 수 있습니다. 변경 내용을 확인 해야 합니다.는 **DSL 탐색기**, Dsl 패키지 프로젝트의 속성 및 어셈블리 정보입니다.

### <a name="to-change-the-namespace-of-a-domain-specific-language"></a>도메인 특정 언어의 네임 스페이스를 변경 하려면

1.  **DSL 탐색기**, 클릭는 **Dsl** 노드.

2.  에 **속성** 창에서 변경 된 **Namespace** 속성입니다.

3.  솔루션을 저장 하 고 템플릿이 변환 합니다.

4.  에 **프로젝트** 메뉴를 클릭 하 여 **Dsl 속성**합니다.

     프로젝트에 대 한 속성이 표시 됩니다.

5.  **응용 프로그램** 탭을 클릭합니다.

6.  변경 된 **기본 네임 스페이스** 속성을 새 네임 스페이스 이름입니다.

7.  어셈블리의 이름을 변경 하려면 변경 된 **어셈블리 이름 속성입니다.**

8.  어셈블리 이름을 변경한 경우 DslPackage\Package.tt 열고이 줄을 업데이트 합니다.

     `string dslAssembly = "YourDSLassembly.Dsl.dll";`

9. 사용자 지정 코드를 작성 한 경우에 코드 파일에서 네임 스페이스 및 클래스 참조를 변경 해야 합니다.

10. Visual Studio 실험적 인스턴스를 다시 설정 합니다.

    1.  삭제 **\Users\\ ***{name}*** \AppData\Local\Microsoft\VisualStudio\\\*Exp**

    2.  Windows **시작** 메뉴 선택 **모든 프로그램**, **Microsoft Visual Studio 2010 SDK**, **도구**, **다시 설정 된 실험적 인스턴스**합니다.

11. 에 **빌드** 메뉴 선택 **솔루션 다시 빌드**합니다.

## <a name="see-also"></a>참고자료

- [도메인 특정 언어 도구 용어집](http://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)