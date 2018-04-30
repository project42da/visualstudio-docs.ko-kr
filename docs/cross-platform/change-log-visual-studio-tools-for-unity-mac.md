---
title: 변경 로그(Visual Studio Tools for Unity, Mac) | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.technology: vs-unity-tools
ms.topic: conceptual
ms.assetid: 33a6ac54-d997-4308-b5a0-af7387460849
author: dantogno
ms.author: v-davian
manager: crdun
ms.workload:
- unity
ms.openlocfilehash: d43542dc78c8bc0eaeb05e1a620edff7a88efa37
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="change-log-visual-studio-tools-for-unity-mac"></a>변경 로그(Visual Studio Tools for Unity, Mac)
Visual Studio Tools for Unity에 대한 변경 로그입니다.

## <a name="1501"></a>1.5.0.1
 릴리스됨 2018-03-28
 
### <a name="new-features"></a>새 기능

-   **통합:**

    -   Unity 프로젝트 탐색기에서 추가 템플릿에 대한 지원이 추가되었습니다.

## <a name="1500"></a>1.5.0.0
 릴리스됨 2018-03-21
 
### <a name="new-features"></a>새 기능

-   **통합:**

    -   USB로 연결된 Android 플레이어에 연결 및 검색에 대한 지원이 추가되었습니다.

## <a name="1403"></a>1.4.0.3
 릴리스됨 2018-03-05
 
### <a name="new-features"></a>새 기능

-   **Project Generation:**

    -   Unity 2018.1에서 새 프로젝트 생성기에 대한 지원이 추가되었습니다.

-   **통합:**

    -   전용 설정에 대한 옵션 패널이 추가되었습니다.

## <a name="1402"></a>1.4.0.2
 릴리스됨 2018-01-24
 
### <a name="bug-fixes"></a>버그 수정

-   **Project Generation:**

    -   Mono 버전 검색이 수정되었습니다.

-   **통합:**

    -   2018.1 및 플러그 인 활성화의 타이밍 문제가 수정되었습니다.

    -   새 플레이어를 검색하는 경우 알림이 수정되었습니다.

## <a name="1401"></a>1.4.0.1
 릴리스됨 2018-01-23
 
### <a name="bug-fixes"></a>버그 수정

-   **통합:**

    -   두 번 클릭 시 확장/축소 폴더 수정함

## <a name="1400"></a>1.4.0.0
 릴리스됨 2017-12-13
 
### <a name="new-features"></a>새 기능

-   **Project Generation:**

    -   .NET Standard에 대한 지원이 추가되었습니다.

### <a name="bug-fixes"></a>버그 수정

-   **통합:**

    -   자동 pdb에서 mdb로의 디버그 기호 변환을 수정했습니다.

## <a name="1301"></a>1.3.0.1
 릴리스됨 2017-12-12
 
### <a name="bug-fixes"></a>버그 수정

-   **통합:**

    -   배열 크기를 변경하는 동안 검사기에 영향을 주는 EditorPrefs.GetBool에 대한 간접 호출이 수정되었습니다.

-   **마법사:**

    -   메서드를 삽입하기 전에 roslyn 컨텍스트를 새로 고칩니다.

## <a name="1300"></a>1.3.0.0
 릴리스됨 2017-11-20
 
### <a name="new-features"></a>새 기능

-   **마법사:**

    -   "Unity 메시지 구현" 마법사가 추가되었습니다.

    -   Mac 7.4용 VS에서 새 완성 API에 대한 지원이 추가되었습니다.

## <a name="1200"></a>1.2.0.0
 릴리스됨 2017-10-23
 
### <a name="new-features"></a>새 기능

-   **디버거:**

    -   휴대용 디버그 기호 파일에 대한 지원을 추가했습니다.

### <a name="bug-fixes"></a>버그 수정

-   **Project Generation:**

    -   어셈블리 파일 이름에 잘못 추가된 추가 .dll 확장명을 수정했습니다.

    -   이제 기본값이 'true'이므로 AllowAttachedDebuggingOfEditor Unity 플래그를 강제하지 않습니다.

## <a name="1103"></a>1.1.0.3
 릴리스됨 2017-10-23
 
### <a name="new-features"></a>새 기능

-   **Project Generation:**

    -   .NET 4.6 프로필에 대한 지원이 추가되었습니다.

## <a name="1102"></a>1.1.0.2
 릴리스됨 2017-08-08
 
### <a name="new-features"></a>새 기능

-   **디버거:**

    -   어떤 Unity에 연결할지 확실하지 않은 경우 프로세스에 연결 대화 상자를 시작합니다.

-   **Project Generation:**

    -   Unity 5.6을 사용할 경우 안전하지 않은 컴파일 스위치를 항상 사용하도록 설정합니다.

## <a name="1101"></a>1.1.0.1
 릴리스됨 2017-07-20
 
### <a name="new-features"></a>새 기능

-   **통합:**

    -   지역화된 리소스에 대한 지원이 추가되었습니다.

## <a name="1100"></a>1.1.0.0
 릴리스됨 2017-07-12
 
### <a name="new-features"></a>새 기능

-   **통합:**

    -   프로세스에 연결 창을 통해 플레이어와 편집기에 연결에 대한 지원이 추가되었습니다.

-   **Project Generation:**

    -   mcs.rsp 파일을 사용한 어셈블리 이름 참조를 수정했습니다.

    -   assembly.json 컴파일 단위 지원이 추가되었습니다.    

    -   API 수준을 사용한 정의를 수정했습니다.    

### <a name="bug-fixes"></a>버그 수정

-   **통합:**

    -   컴파일할 때 셰이더 오류 메시지를 수정했습니다.

## <a name="1001"></a>1.0.0.1
 릴리스됨 2017-05-04
 
### <a name="bug-fixes"></a>버그 수정

-   **통합:**

    -   하이브리드 및 일반 프로젝트를 사용하여 활성 문서 추적을 수정했습니다.

## <a name="1000"></a>1.0.0.0
 릴리스됨 2017-05-03
