---
title: Node.js 및 React 앱 만들기
description: 이 자습서에서는 Visual Studio용 Node.js 도구를 사용하여 앱을 만듭니다.
ms.custom: mvc
ms.date: 02/19/2018
ms.technology: vs-nodejs
ms.topic: tutorial
ms.devlang: javascript
author: mikejo5000
ms.author: mikejo
manager: douge
dev_langs:
- JavaScript
ms.workload:
- nodejs
ms.openlocfilehash: 9958711ea64daee9876d3b16330685786b6d5825
ms.sourcegitcommit: b400528a83bea06d208d95c77282631ae4a93091
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/23/2018
---
# <a name="tutorial-create-a-nodejs-and-react-app-in-visual-studio"></a>자습서: Visual Studio에서 Node.js 및 React 앱 만들기
Visual Studio를 사용하면 쉽게 Node.js 프로젝트를 만들고 IntelliSense 및 Node.js를 지원하는 다른 기본 제공 기능을 활용할 수 있습니다. Visual Studio용 이 자습서에서는 Visual Studio 템플릿에서 Node.js 웹 응용 프로그램 프로젝트를 만듭니다. 그런 다음, React를 사용하여 간단한 앱을 만듭니다.

이 자습서에서는 다음 방법을 학습합니다.
> [!div class="checklist"]
> * Node.js 프로젝트 만들기
> * NPM 패키지 추가
> * 앱에 React 코드 추가
> * JSX 트랜스파일
> * 디버거 연결

## <a name="prerequisites"></a>전제 조건

* Node.js 개발 워크로드와 Visual Studio 2017이 설치되어 있어야 합니다.

    아직 Visual Studio를 설치하지 않은 경우 [여기](http://www.visualstudio.com)에서 평가판을 설치합니다.

    워크로드를 설치해야 하지만 이미 Visual Studio가 있는 경우 **새 프로젝트** 대화 상자의 왼쪽 창에서 **Open Visual Studio 설치 관리자** 링크를 클릭합니다. Visual Studio 설치 관리자가 시작됩니다. **Node.js 개발** 워크로드를 선택한 다음 **수정**을 선택합니다.

* Node.js 런타임을 설치해야 합니다.

    아직 설치되지 않은 경우 [Node.js](https://nodejs.org/en/download/) 웹 사이트에서 LTS 버전을 설치합니다. 일반적으로, 설치된 Node.js 런타임은 Visual Studio에서 자동으로 검색됩니다. 설치된 런타임이 검색되지 않으면 속성 페이지에서 설치된 런타임을 참조하도록 프로젝트를 구성할 수 있습니다(프로젝트를 만든 후 프로젝트 노드를 마우스 오른쪽 단추로 클릭하고 **속성**을 선택합니다).

    이 자습서는 버전 8.9.4를 사용하여 테스트했습니다.

## <a name="create-a-project"></a>프로젝트 만들기
먼저 Node.js 웹 응용 프로그램 프로젝트를 만듭니다.

1. Visual Studio 2017을 엽니다.

1. 메뉴 모음에서 **파일** > **새로 만들기** > **프로젝트...** 를 차례로 선택합니다.

1. **새 프로젝트** 대화 상자의 왼쪽 창에서 **JavaScript**를 확장한 후 **Node.js**를 선택합니다. 가운데 창에서 **빈 Node.js 웹 응용 프로그램**을 선택하고 **NodejsWebAppBlank**의 이름을 입력한 다음, **확인**을 선택합니다.

     **빈 Node.js 웹 응용 프로그램** 프로젝트 템플릿이 표시되지 않으면 먼저 Node.js 개발 워크로드를 설치해야 합니다.

    Visual Studio가 새 솔루션을 만들고 프로젝트를 엽니다.

    ![솔루션 탐색기에서 Node.js 프로젝트](../nodejs/media/tutorial-nodejs-react-project-structure.png)

    - 굵게 강조 표시된 것은 **새 프로젝트** 대화 상자에서 지정한 이름을 사용하는 프로젝트입니다. 파일 시스템에서 이 프로젝트는 프로젝트 폴더의 *.njsproj* 파일로 표시됩니다. 속성을 마우스 오른쪽 단추로 클릭하고 **속성**을 선택하여 프로젝트와 연결된 환경 변수와 속성을 설정할 수 있습니다. 프로젝트 파일이 Node.js 프로젝트 소스에 사용자 지정 변경을 하지 않으므로 다른 개발 도구와 라운드트립을 수행할 수 있습니다.

    - 최상위 수준은 기본적으로 프로젝트와 이름이 동일한 솔루션입니다. 디스크에서 *.sln* 파일로 표시되는 솔루션은 하나 이상의 관련된 프로젝트에 대한 컨테이너입니다.

    - npm 노드에는 설치된 npm 패키지가 있으면 표시됩니다. npm 노드를 마우스 오른쪽 버튼으로 클릭하고 대화 상자를 사용하여 npm 패키지를 검색하고 설치할 수 있습니다.

    - *server.js*와 같은 프로젝트 파일은 프로젝트 노드 아래 표시됩니다. *server.js*는 프로젝트 시작 파일입니다.

## <a name="add-npm-packages"></a>NPM 패키지 추가

이 앱이 제대로 실행되려면 많은 npm 모듈이 필요합니다.

* react
* react-dom
* express
* path
* ts-loader
* typescript
* webpack
* webpack-cli

1. 솔루션 탐색기(오른쪽 창)의 프로젝트에서 **npm** 노드를 마우스 오른쪽 버튼으로 클릭하고 **새 npm 패키지 설치**를 선택합니다.

    **새 npm 패키지 설치** 대화 상자에서 최신 패키지 버전 설치 또는 버전 지정을 선택할 수 있습니다. 이러한 패키지의 현재 버전 설치를 선택하고 나중에 예기치 않은 오류가 발생하면 나중에 이러한 단계에서 설명된 정확한 패키지 버전을 설치해야 할 수 있습니다.

1. **새 npm 패키지 설치** 대화 상자에서 React 패키지를 검색하고 **패키지 설치**를 클릭해 설치합니다.

    ![npm 패키지 설치](../nodejs/media/tutorial-nodejs-react-install-packages.png)

    **출력** 창에 패키지를 설치하는 진행률이 표시됩니다. 설치 시 패키지가 **npm** 노드 아래 표시됩니다.

    프로젝트의 *package.json* 파일은 패키지 버전을 포함하여 새 패키지 정보로 업데이트됩니다.

1. UI를 사용하여 나머지 패키지를 한 번에 하나씩 검색하고 추가하는 대신 package.json에 다음 코드를 붙여넣습니다. `dependencies` 섹션을 이 코드로 바꿉니다.

    ```js
    "dependencies": {
      "express": "4.16.2",
      "path": "0.12.7",
      "react": "16.2.0",
      "react-dom": "16.2.0",
      "ts-loader": "4.0.1",
      "typescript": "2.7.2",
      "webpack": "4.1.1",
      "webpack-cli": "2.0.11"
    }
    ```

1. 프로젝트에서 **npm** 노드를 마우스 오른쪽 단추로 클릭하고 **누락된 npm 패키지 설치**를 선택합니다.

    **출력** 창에 패키지를 설치하는 진행률이 표시됩니다.

    설치된 후 솔루션 탐색기에 표시된 대로 여기 npm 모듈이 있습니다.

    ![NPM 패키지](../nodejs/media/tutorial-nodejs-react-npm-modules.png)

    > [!NOTE]
    > 명령줄을 사용하여 npm 패키지를 설치하려면 프로젝트 노드를 마우스 오른쪽 단추로 클릭하고 **여기서 명령 프롬프트 열기**를 선택합니다. 표준 Node.js 명령을 사용하여 패키지를 설치합니다.

## <a name="add-project-files"></a>프로젝트 파일 추가

이러한 단계에서는 프로젝트에 새 파일 4개를 추가합니다.

* *app.tsx*
* *webpack-config.js*
* *index.html*
* *tsconfig.json*

이 간단한 앱에 대해서는 프로젝트 루트에서 새 프로젝트 파일을 추가합니다. (대부분의 앱에서 일반적으로 하위 폴더에 파일을 추가하고 상대 경로 참조를 적절하게 조정합니다.)

1. 솔루션 탐색기에서 **NodejsWebAppBlank** 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가** > **새 항목**을 선택합니다.

1. **새 항목 추가** 대화 상자에서 **TypeScript JSX 파일**을 선택하고 *app.tsx* 이름을 입력하고 **확인**을 클릭합니다.

1. *webpack-config.js*를 추가하려면 이러한 단계를 반복합니다.

1. *index.html*을 프로젝트에 추가하려면 동일한 단계를 반복합니다. JavaScript 파일 대신 **HTML 파일**을 선택합니다.

1. *tsconfig.json*을 프로젝트에 추가하려면 동일한 단계를 반복합니다. JavaScript 파일 대신 **TypeScript JSON 구성 파일**을 선택합니다.

## <a name="add-app-code"></a>앱 코드 추가

1. *server.js*를 열고 코드를 다음 코드로 바꿉니다.

    ```javascript
    'use strict';
    var path = require('path');
    var express = require('express');

    var app = express();

    var staticPath = path.join(__dirname, '/');
    app.use(express.static(staticPath));

    // Allows you to set port in the project properties.
    app.set('port', process.env.PORT || 3000);

    var server = app.listen(app.get('port'), function() {
        console.log('listening');
    });
    ```

   이전 코드는 Express를 사용하여 웹 응용 프로그램 서버로 Node.js를 시작합니다. 위의 코드는 프로젝트 속성에서 구성된 포트 번호에 포트를 설정합니다(기본적으로 포트는 구성 속성에서 1337로 구성됩니다). 프로젝트 속성을 열려면 솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **속성**을 선택합니다.

1. *app.tsx*를 열고 다음 코드를 추가합니다.

    ```javascript
    declare var require: any

    var React = require('react');
    var ReactDOM = require('react-dom');

    class Hello extends React.Component {
        render() {
            return (
                <h1>Welcome to React!!</h1>
            );
        }
    }

    ReactDOM.render(<Hello />, document.getElementById('root'));
    ```

    위의 코드는 JSX 구문과 React를 사용하여 간단한 메시지를 표시합니다.

1. *index.html*을 열고 **body** 섹션을 다음 코드로 바꿉니다.

    ```html
    <body>
        <div id="root"></div>
        <!-- scripts -->
        <script src="./dist/app-bundle.js"></script>
    </body>
    ```

    이 HTML 페이지는 일반 JavaScript로 트랜스파일된 JSX 및 React 코드를 포함하는 *app-bundle.js*를 로드합니다. 현재 *app-bundle.js*는 빈 파일입니다. 다음 섹션에서 코드를 트랜스파일하는 옵션을 구성합니다.

## <a name="configure-webpack-and-typescript-compiler-options"></a>Webpack 및 TypeScript 컴파일러 옵션 구성

위의 단계에서 *webpack-config.js*를 프로젝트에 추가했습니다. 다음으로, webpack 구성 코드를 추가 합니다. JSX를 일반 JavaScript로 번들 및 트랜스파일하려면 입력 파일(*app.tsx*) 및 출력 파일(*app-bundle.js*)을 지정하는 간단한 webpack 구성을 추가합니다. 트랜스파일하려면 일부 TypeScript 컴파일러 옵션을 구성합니다. 이 코드는 webpack 및 TypeScript 컴파일러를 도입하려는 기본 구성입니다.

1. 솔루션 탐색기에서 *webpack-config.js*를 열고 다음 코드를 추가합니다.

    ```json
    module.exports = {
        devtool: 'source-map',
        entry: "./app.tsx",
        mode: "development",
        output: {
            filename: "./app-bundle.js"
        },
        resolve: {
            extensions: ['.Webpack.js', '.web.js', '.ts', '.js', '.jsx', '.tsx']
        },
        module: {
            rules: [
                {
                    test: /\.tsx$/,
                    exclude: /(node_modules|bower_components)/,
                    use: {
                        loader: 'ts-loader'
                    }
                }
            ]
        }
    }
    ```

    Webpack 구성 코드는 Webpack에게 TypeScript 로더를 사용해 JSX를 트랜스파일하도록 지시합니다.

1. tsconfig.json을 열고 다음 코드를 추가하여 TypeScript 컴파일러 옵션을 지정합니다.

    ```json
    {
      "compilerOptions": {
        "noImplicitAny": false,
        "module": "commonjs",
        "noEmitOnError": true,
        "removeComments": false,
        "sourceMap": true,
        "target": "es5",
        "jsx": "react"
      },
      "exclude": [
        "node_modules"
      ],
      "files": [
        "app.tsx"
      ]
    }
    ```

    소스 파일로 app.tsx를 지정합니다.

## <a name="transpile-the-jsx"></a>JSX 트랜스파일

1. 솔루션 탐색기에서 프로젝트 노드를 마우스 오른쪽 단추로 클릭하고 **여기서 명령 프롬프트 열기**를 선택합니다.

1. 명령 프롬프트에 다음 명령을 입력합니다.

    `node_modules\.bin\webpack app.tsx --config webpack-config.js`

    명령 프롬프트 창에 결과가 표시됩니다.

    ![webpack 실행](../nodejs/media/tutorial-nodejs-react-run-webpack.png)

    위의 출력 대신 오류를 참조하면 앱이 작동하기 전에 해당 오류를 해결해야 합니다. npm 패키지 버전이이 자습서에 표시된 버전과 다른 경우 오류의 원인이 될수 있습니다. 오류를 수정하는 한 방법은 이전 단계에서 표시된 정확한 버전을 사용하는 것입니다. 또한 이러한 패키지 버전 중 하나 이상이 사용되지 않아 오류를 일으킬 경우 오류를 수정하려면 최신 버전을 설치해야 합니다.

1. 솔루션 탐색기에서 프로젝트 노드를 마우스 오른쪽 단추로 클릭하고 **추가** > **기존 폴더**를 선택한 다음, *dist* 폴더를 선택하고 **폴더 선택**을 클릭합니다.

    Visual Studio는 *app-bundle.js* 및 *app-bundle.js.map*을 포함하는 프로젝트에 *dist* 폴더를 추가합니다.

1. *app-bundle.js*를 열고 트랜스파일된 JavaScript 코드를 봅니다.

1. 외부에서 수정된 파일을 다시 로드하라는 메시지가 나타나면 **모두 예**를 클릭합니다.

    ![수정한 파일 로드](../nodejs/media/tutorial-nodejs-react-reload-files.png)

*app.tsx*를 변경할 때마다 webpack 명령을 다시 실행해야 합니다.

## <a name="run-the-app"></a>앱 실행

1. 크롬이 현재 디버그 대상으로 선택되었는지 확인 합니다.

    ![디버그 대상으로 크롬 선택](../nodejs/media/tutorial-nodejs-react-debug-target.png)

1. 앱을 실행하려면 **F5**(**디버그** > **디버깅 시작**) 키 또는 녹색 화살표 단추를 누릅니다.

    디버거가 수신 대기하는 포트를 보여주는 Node.js 콘솔 창이 열립니다.

    Visual Studio는 *server.js* 시작 파일을 시작하여 앱을 시작합니다.

    ![브라우저에서 React 실행](../nodejs/media/tutorial-nodejs-react-running-react.png)

1. 브라우저 창을 닫습니다.

1. 콘솔 창을 닫습니다.

## <a name="set-a-breakpoint-and-run-the-app"></a>중단점 설정 및 앱 실행

1. *server.js*에서 `staticPath` 선언 왼쪽의 여백을 클릭해 중단점을 설정합니다.

    ![중단점 설정](../nodejs/media/tutorial-nodejs-react-set-breakpoint.png)

    중단점은 신뢰할 수 있는 디버깅의 가장 기본적이 고 필수적인 기능입니다. 중단점은 변수의 값, 메모리의 동작 또는 코드 분기의 실행 여부를 확인할 수 있도록 Visual Studio에서 실행 중인 코드를 일시 중단해야 하는 위치를 나타냅니다.

1. 앱을 실행하려면 **F5**(**디버그** > **디버깅 시작**) 키를 누릅니다.

    디버거는 설정한 중단점에서 일시 중지합니다(현재 명령문은 노란색으로 표시됩니다). 이제 **로컬** 및 **조사식** 창과 같은 디버거 창을 사용하여 현재 범위 내에 있는 변수를 가리킴으로써 앱 상태를 검사할 수 있습니다.

1. 앱을 계속하려면 **F5** 키를 누릅니다.

1. 크롬 개발자 도구를 사용하려는 경우 **F12** 키를 누릅니다. JavaScript 콘솔을 사용하여 앱과 상호 작용하고 DOM을 검사하려면 이러한 도구를 사용할 수 있습니다.

1. 콘솔 및 웹 브라우저를 닫습니다.

## <a name="set-and-hit-a-breakpoint-in-the-client-side-react-code"></a>클라이언트 쪽 React 코드에서 중단점 설정 및 적중

이전 섹션에서 서버 쪽 Node.js 코드에 디버거를 연결했습니다. Visual Studio에서 디버거를 연결하고 클라이언트 쪽 React 코드에서 중단점을 적중하려면 디버거는 올바른 프로세스를 식별하기 위한 도움이 필요합니다. 이를 사용하는 한 방법은 다음과 같습니다.

1. 모든 크롬 창을 닫습니다.

1. Windows **시작** 단추(**실행**을 마우스 오른쪽 단추로 클릭하고 선택)에서 **실행** 명령을 열고 다음 명령을 입력합니다.

    `chrome.exe --remote-debugging-port=9222`

    디버깅 사용이 설정된 상태로 크롬을 시작합니다.

1. 다음 그림에 표시된 것처럼 Visual Studio로 전환하고 `render()` 기능의 *app-bundle.js* 코드에서 중단점을 설정합니다.

    ![중단점 설정](../nodejs/media/tutorial-nodejs-react-set-breakpoint-client-code.png)

1. Visual Studio에서 디버그 대상으로 선택된 크롬을 사용하여 **Ctrl + F5**(**디버그** > **디버깅하지 않고 시작**) 키를 눌러 브라우저에서 앱을 실행합니다.

    앱이 새 브라우저 탭에서 열립니다.

1. **디버그** > **프로세스에 연결**을 선택합니다.

1. **프로세스에 연결** 대화 상자의 **연결** 필드에서 **Webkit 코드**를 선택하고 필터 상자에 **크롬**을 입력해 검색 결과를 필티링합니다.

1. 올바른 호스트 포트(이 예제에서는 1337)를 사용하여 크롬 프로세스를 선택하고 **연결**을 클릭합니다.

    ![프로세스에 연결](../nodejs/media/tutorial-nodejs-react-attach-to-process.png)

    DOM 탐색기와 JavaScript 콘솔이 Visual Studio에서 열릴 때 디버거가 올바르게 연결됐는지 알 수 있습니다. 이러한 디버깅 도구는 크롬 개발자 도구 및 F12 Tools for Edge와 유사합니다.

    > [!NOTE]
    > 디버거가 연결되지 않고 “프로세스에 연결할 수 없습니다. 현재 상태에서는 작업을 수행할 수 없습니다.”라는 메시지가 표시되는 경우 디버깅 모드로 Chrome을 시작하기 전에 작업 관리자를 사용하여 Chrome의 모든 인스턴스를 닫습니다. 크롬 확장 프로그램을 실행하여 전체 디버그 모드를 방지할 수 있습니다.

1. 중단점이 있는 코드가 이미 실행됐기 때문에 중단점을 적중하려면 브라우저 페이지를 새로 고치기 합니다.

    디버거에서 일시 중지된 동안 변수를 가리키고 디버거 창을 사용하여 앱 상태를 검사할 수 있습니다. 단계별 코드 실행(**F5**, **F10** 및 **F11**)으로 디버거로 이동할 수 있습니다 .

    환경 및 브라우저 상태에 따라 *app.tsx*에서 매핑된 위치 또는 *app-bundle.js*에서 중단점을 적중할 수 있습니다. 어느 경우든 단계별 코드를 실행하고 변수를 검사할 수 있습니다.

    * *app.tsx*에서 코드를 중단해야 하는데 그럴 수 없는 경우 이전 단계에 설명된 대로 **프로세스에 연결**을 사용하여 디버거를 연결합니다. 그런 다음, **스크립트 문서** > **app.tsx**를 열어 솔루션 탐색기에서 동적으로 생성된 *app.tsx* 파일을 열고, 중단점을 설정하고, 브라우저에서 페이지를 새로 고칩니다.

        또는 *app.tsx*에서 코드를 중단해야 하는데 그럴 수 없는 경우 *app.tsx*에서 `debugger;` 문을 사용하거나 대신 Chrome 개발자 도구에서 중단점을 설정합니다.

    * *app-bundle.js*에서 코드를 중단해야 하는데 그럴 수 없는 경우 *app-bundle.js.map* 소스 맵 파일을 제거합니다.

    > [!TIP]
    > 이러한 단계를 수행하여 처음으로 프로세스에 연결할 때 **디버그** > **프로세스에 다시 연결**을 선택하여 Visual Studio 2017에서 동일 프로세스에 신속하게 다시 연결할 수 있습니다.

## <a name="next-steps"></a>다음 단계

이 자습서에서는 Node.js 및 React 앱을 만들고 JSX 및 디버그를 트랜스파일하는 방법을 배웠습니다. Visual Studio용 Node.js 도구에 대해 자세히 알려면 Wiki 페이지를 참조하세요.

> [!div class="nextstepaction"]
> [Visual Studio용 Node.js 도구](https://github.com/Microsoft/nodejstools)
