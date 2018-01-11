---
title: "빠른 시작: Visual Studio를 사용하여 첫 번째 Node.js 앱 만들기 | Microsoft Docs"
ms.custom: 
ms.date: 11/15/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-acquisition
ms.tgt_pltfrm: 
ms.topic: quickstart
ms.devlang: javascript
ms.assetid: b0e4ebed-1a01-41ef-aad1-4d8465ce5322
author: mikejo5000
ms.author: mikejo
manager: ghogen
dev_langs: JavaScript
ms.workload: nodejs
ms.openlocfilehash: 12c848797b167038b02106ca3392cac50171f699
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="quickstart-use-visual-studio-to-create-your-first-nodejs-app"></a>빠른 시작: Visual Studio를 사용하여 첫 번째 Node.js 앱 만들기
Visual Studio IDE(통합 개발 환경)에 대한 이 5~10분 분량의 소개에서는 간단한 Node.js 웹 응용 프로그램을 만듭니다. 아직 Visual Studio를 설치하지 않은 경우 [여기](http://www.visualstudio.com)에서 평가판을 설치합니다.  

## <a name="create-a-project"></a>프로젝트 만들기
먼저, Node.js 웹 응용 프로그램 프로젝트를 만듭니다.

1. Visual Studio 2017을 엽니다.  

2. 메뉴 모음에서 **파일** > **새로 만들기** > **프로젝트...**를 차례로 선택합니다.  

3. **새 프로젝트** 대화 상자의 왼쪽 창에서 **JavaScript**를 확장한 후 **Node.js**를 선택합니다. 가운데 창에서 **빈 Node.js 웹 응용 프로그램**을 선택한 후 **확인**을 선택합니다.   

     **빈 Node.js 웹 응용 프로그램** 프로젝트 템플릿이 표시되지 않으면 **새 프로젝트** 대화 상자의 왼쪽 창에서 **Visual Studio 설치 관리자 열기** 링크를 클릭합니다. Visual Studio 설치 관리자가 시작됩니다. **Node.js 개발** 워크로드를 선택한 다음 **수정**을 선택합니다.  

     ![VS 설치 관리자에서 Node.js 워크로드](../ide/media/quickstart-nodejs-workload.png)  

    Visual Studio에서 새 솔루션을 만들고 프로젝트를 엽니다. **server.js**가 편집기에서 열립니다.

## <a name="explore-the-ide"></a>IDE 탐색  

1. 오른쪽 창에서 **솔루션 탐색기**를 살펴봅니다.

   ![솔루션 탐색기](../ide/media/quickstart-nodejs-solution-explorer.png)  

  - 굵게 강조 표시된 것은 **새 프로젝트** 대화 상자에서 지정한 이름을 사용하는 프로젝트입니다. 디스크에서 이 프로젝트는 프로젝트 폴더의 .njsproj 파일로 표시됩니다.

  - 최상위 수준은 기본적으로 프로젝트와 이름이 동일한 솔루션입니다. 디스크에서 .sln 파일로 표시되는 솔루션은 하나 이상의 관련된 프로젝트에 대한 컨테이너입니다.

  - npm 노드에는 설치된 npm 패키지가 있으면 표시됩니다. npm 노드를 마우스 오른쪽 버튼으로 클릭하고 대화 상자를 사용하여 npm 패키지를 검색하고 설치할 수 있습니다.

1. 명령 프롬프트에서 npm 패키지 또는 node.js 명령을 설치하려면 프로젝트 노드를 마우스 오른쪽 단추로 클릭하고 **여기서 명령 프롬프트 열기**를 선택합니다.

   ![Node.js 명령 프롬프트](../ide/media/quickstart-nodejs-command-prompt.png) 

1. 편집기(왼쪽 창)의 **server.js** 파일에서 `http.createServer`를 선택한 후 **F12** 키를 누르거나 상황에 맞는 메뉴에서(마우스 오른쪽 단추 클릭) **정의로 이동**을 선택합니다. 이 명령을 실행하면 index.d.ts에 있는 `createServer` 함수에 대한 정의가 표시됩니다.  

   ![[정의로 이동] 바로 가기 메뉴](../ide/media/quickstart-nodejs-gotodefinition.png)  

1. 이 코드 줄, `res.end('Hello World\n');`의 문자열 끝 부분에 커서를 놓고 다음과 같이 수정합니다.

    `res.end('Hello World\n' + res.connection.`

    `connection.`을 입력한 부분에 IntelliSense가 코드 입력을 자동 완성하는 옵션을 제공합니다.

   ![IntelliSense 자동 완성](../ide/media/quickstart-nodejs-intellisense.png)  

1. **localPort**를 선택한 다음 `);`을 입력하고 명령문을 완성하면 다음과 같이 표시됩니다.

    `res.end('Hello World\n' + res.connection.localPort);`

## <a name="run-the-application"></a>응용 프로그램 실행
1. **Ctrl+F5**(또는 **디버그 > 디버깅하지 않고 시작**)를 눌러서 응용 프로그램을 실행합니다. 앱이 브라우저에서 열립니다.  

1. 브라우저 창에 "Hello World"와 로컬 포트 번호가 표시됩니다.

1. 웹 브라우저를 닫습니다.  

이 빠른 시작을 완료한 것을 축하 드립니다! Visual Studio IDE를 이해하는 데 도움이 되었기를 바랍니다. 해당 기능을 보다 자세히 알아보려면 목차에서 **자습서** 섹션에 있는 자습서를 읽어보세요.  

## <a name="next-steps"></a>다음 단계 

- [Node.js에 대한 자습서](../nodejs/tutorial-nodejs.md) 살펴보기  
- [Visual Studio IDE](../ide/visual-studio-ide.md)에 대해 자세히 알아보기  
- [Visual Studio용 Node.js 도구](https://github.com/Microsoft/nodejstools/wiki)에 대해 자세히 알아보기