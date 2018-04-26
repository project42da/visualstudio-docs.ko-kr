---
title: 워크플로 디자이너-(레거시) 원격 컴퓨터에서 워크플로 디버깅
ms.date: 11/04/2016
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
helpviewer_keywords:
- workflows, debugging remotely
- debugging workflows, remotely
- remote debugging, workflows
- debugging, remote
ms.assetid: 44eaec8f-9959-4ae7-a374-670946f933c1
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 391180cd76fe5e0cccca802ba1cbfb78277dabc1
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="debugging-workflows-from-a-remote-computer-legacy"></a>원격 컴퓨터에서 워크플로 디버깅(레거시)

이 항목에서는 레거시 Windows Workflow Designer로 빌드된 원격 레거시 Windows WF (Workflow Foundation) 응용 프로그램을 디버깅 하는 방법에 설명 합니다. 응용 프로그램의 WinFX 또는.NET Framework 버전 3.5 대상으로 해야 하는 경우 레거시 워크플로 디자이너를 사용 합니다.

 Visual Studio를 설치할 때의 Visual Studio 디버거에 대 한 Windows WF (Workflow Foundation)를 설치 하는 구성 요소 설치 옵션 중 하나입니다. 원격 디버깅 구성 요소가 설치됩니다. 이 원격 디버깅 구성 요소는 원격 워크플로 디버깅의 대상 컴퓨터에 설치해야 합니다.

 또한 디버깅을 수행하는 데 사용되는 로컬 컴퓨터의 GAC(전역 어셈블리 캐시)에 원격 컴퓨터에서 디버깅할 레거시 워크플로의 워크플로 정의가 포함된 어셈블리를 설치해야 합니다. 예를 들어 원격 컴퓨터 A에서 실행 중인 레거시 워크플로를 로컬 컴퓨터 B에서 디버깅하는 경우, 워크플로 정의가 컴퓨터 B의 GAC에 있어야 합니다. 그러면 디자이너가 원격 컴퓨터 A에서 실행 중인 워크플로의 워크플로 마크업을 deserialize하고 컴퓨터 B에 표시할 수 있습니다. 전역 어셈블리 캐시에 대한 자세한 내용은 MSDN Library를 참조하십시오.

 Windows Workflow Foundation 원격 디버깅은 다른 Visual Studio 구성 요소의 원격 디버깅과 동일하게 작동합니다. 자세한 내용은 Visual Studio 원격 디버깅 MSDN 라이브러리의을 참조 하십시오.

## <a name="see-also"></a>참고자료

- [레거시 워크플로 디버깅](../workflow-designer/debugging-legacy-workflows.md)