---
title: "Visual Studio에서 Node.js 시작 | Microsoft 문서"
ms.custom: 
ms.date: 11/30/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-acquisition
ms.tgt_pltfrm: 
ms.topic: tutorial
ms.devlang: javascript
author: mikejo5000
ms.author: mikejo
manager: ghogen
dev_langs:
- JavaScript
ms.workload:
- nodejs
ms.openlocfilehash: a8e6c800ef036d0f6e8e5affae745e541a276284
ms.sourcegitcommit: d6327b978661c0a745bf4b59f32d8171607803a3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/01/2018
---
# <a name="getting-started-with-nodejs-in-visual-studio"></a>Visual Studio에서 Node.js 시작
Visual Studio를 사용하여 Node.js를 개발하기 위한 이 자습서에서는 Node.js 웹 응용 프로그램을 만들고, 일부 코드를 추가하며, IDE의 일부 기능을 살펴보고, 앱을 실행합니다.  아직 Visual Studio를 설치하지 않은 경우 [여기](http://www.visualstudio.com)에서 평가판을 설치합니다.  

## <a name="create-a-project"></a>프로젝트 만들기
먼저 Node.js 웹 응용 프로그램 프로젝트를 만듭니다.

1. Visual Studio 2017을 엽니다.  

2. 메뉴 모음에서 **파일** > **새로 만들기** > **프로젝트...**를 차례로 선택합니다.  

3. **새 프로젝트** 대화 상자의 왼쪽 창에서 **JavaScript**를 확장한 후 **Node.js**를 선택합니다. 가운데 창에서 **기본 Azure Node.js Express 4 응용 프로그램**을 선택한 후 **확인**을 선택합니다.   

     **기본 Azure Node.js Express 4 응용 프로그램** 프로젝트 템플릿이 표시되지 않으면 **새 프로젝트** 대화 상자의 왼쪽 창에서 **Visual Studio 설치 관리자 열기** 링크를 클릭합니다. Visual Studio 설치 관리자가 시작됩니다. **Node.js 개발** 워크로드를 선택한 다음 **수정**을 선택합니다. 

    Visual Studio가 새 솔루션을 만들고 프로젝트를 엽니다. **app.js** 프로젝트 파일이 편집기에 열립니다(왼쪽 창). Visual Studio 솔루션 및 프로젝트를 잘 모르는 경우 [빠른 시작: Visual Studio를 사용하여 첫 번째 Node.js 앱 만들기](../ide/quickstart-nodejs.md)를 참조하세요.

## <a name="add-some-code"></a>일부 코드를 추가합니다.

1. 솔루션 탐색기(오른쪽 창)에서 Views 폴더를 연 다음 index.pug를 엽니다.

1. 콘텐츠를 다음 표시로 바꿉니다.

    ```js
    extends layout

    block content
      h1= title
      p Welcome to #{title}
      script.
        var f1 = function() { document.getElementById('myImage').src='#{data.item1}' }
      script.
        var f2 = function() { document.getElementById('myImage').src='#{data.item2}' }
      script.
        var f3 = function() { document.getElementById('myImage').src='#{data.item3}' }

      button(onclick='f1()') One!
      button(onclick='f2()') Two!
      button(onclick='f3()') Three!
      p
      a: img(id='myImage' height='200' width='200' src='')
    ```

1. Routes 폴더에서 index.js를 엽니다.

1. `router.get` 호출 앞에 다음 코드를 추가합니다.

    ```js
    var getData = function () {
        var data = {
            'item1': 'http://public-domain-photos.com/free-stock-photos-1/flowers/cactus-76.jpg',
            'item2': 'http://public-domain-photos.com/free-stock-photos-1/flowers/cactus-77.jpg',
            'item3': 'http://public-domain-photos.com/free-stock-photos-1/flowers/cactus-78.jpg'
        }
        return data;
    }
    ````

1. `router.get` 함수 호출을 다음 코드로 바꿉니다.

    ```js
    router.get('/', function (req, res) {
        res.render('index', { title: 'Express', "data" });
    });
    ```

1. `data` 다음에 `: get`을 입력하면 IntelliSense가 getData 함수를 표시합니다. `getData`를 선택합니다.

    ![IntelliSense 사용](../nodejs/media/tutorial-nodejs-intellisense.png) 

1. `"data"` 앞의 쉼표(`,`)를 제거하면 해당 식에 녹색의 구문 강조 표시가 나타납니다. 구문 강조 표시 위에 마우스를 가져갑니다.

    ![구문 오류 보기](../nodejs/media/tutorial-nodejs-syntax-checking.png) 

    이 메시지의 마지막 줄에 JavaScript 인터프리터가 쉼표(`,`)를 예상했다는 메시지가 나타납니다.

1. **오류 목록** 탭을 클릭합니다.

    경고 및 설명이 파일 이름 및 줄 번호와 함께 표시됩니다.

    ![오류 목록 보기](../nodejs/media/tutorial-nodejs-error-list.png)

1. `"data"` 앞에 쉼표(`,`)를 추가하여 코드를 수정합니다.

## <a name="set-a-breakpoint"></a>중단점 설정

1. Index.js에서 다음 코드 줄 앞의 왼쪽 여백을 클릭하여 중단점을 설정합니다.

    `res.render('index', { title: 'Express', "data": getData() });`

    중단점은 신뢰할 수 있는 디버깅의 가장 기본적이 고 필수적인 기능입니다. 중단점은 변수의 값, 메모리의 동작 또는 코드 분기의 실행 여부를 확인할 수 있도록 Visual Studio에서 실행 중인 코드를 일시 중단해야 하는 위치를 나타냅니다. 

    ![중단점 설정](../nodejs/media/tutorial-nodejs-set-breakpoint.png) 

## <a name="run-the-application"></a>응용 프로그램 실행

1. 디버그 도구 모음에서의 디버그 대상을 선택합니다.

    ![디버그 대상 선택](../nodejs/media/tutorial-nodejs-deploy-target.png) 

1. **Ctrl+F5**를 눌러 응용 프로그램을 실행합니다.

    디버거가 설정한 중단점에서 일시 중지됩니다. 이제 앱 상태를 검사할 수 있습니다.

1. `getData`에 마우스를 가져가 DataTip에서 속성 보기

    ![변수 검사](../nodejs/media/tutorial-nodejs-inspect-variables.png)

1. **F5**를 눌러 계속합니다.

    앱이 브라우저에서 열립니다.

    브라우저 창에서 제목은 "Express", 첫 단락에 "Welcome to Express"가 표시됩니다.

1. 단추를 클릭하면 다른 이미지가 표시됩니다.

    ![브라우저에서 실행 중인 앱](../nodejs/media/tutorial-nodejs-running-in-browser.png)  

1. **보기 > 다른 창 > Node.js 대화형 창**을 선택하여 Node.js 대화형 창을 엽니다.

   ![Node.js 대화형 창 열기](../nodejs/media/tutorial-nodejs-interactive-window.png)  

    대화형 창은 `require()` 문의 사용을 포함하여 코드에서 수행할 수 있는 모든 항목을 지원합니다. 다음 스크린샷의 코드는 변수를 정의하고 Node.js 인터프리터의 위치를 표시합니다.

   ![Node.js 대화형 창](../nodejs/media/tutorial-nodejs-interactive-window-example.png)  

1. 웹 브라우저를 닫습니다.  

## <a name="optional-publish-to-azure-app-service"></a>(선택 사항) Azure App Service에 게시

1. 솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **게시**를 선택합니다.

   ![Azure App Service에 게시](../nodejs/media/tutorial-nodejs-publish-to-azure.png)  

1. **Microsoft Azure App Service**를 선택합니다.

    **App Service** 대화 상자에서는 Azure 계정에 로그인하여 기존 Azure 구독에 로그인할 수 있습니다.

1. 나머지 단계에 따라 구독을 선택하고, 리소스 그룹을 선택하거나 만들고, 앱 서비스 평면을 만들거나 선택한 다음 Azure에 게시할 때 나타나는 단계를 따릅니다. 자세한 내용은 [웹 배포를 사용하여 Azure 웹 사이트에 게시](https://github.com/Microsoft/nodejstools/wiki/Publish-to-Azure-Website-using-Web-Deploy)를 참조하세요.

1. **출력** 창에서 Azure에 배포하는 진행률이 표시됩니다.

    제대로 배포되면 Azure App Service를 실행하는 브라우저에서 앱이 열립니다. 단추를 클릭하면 이미지가 표시됩니다.

   ![Azure App Service에서 실행 중인 앱](../nodejs/media/tutorial-nodejs-running-in-azure.png)  

축하합니다. 이 자습서를 마쳤습니다.

## <a name="next-steps"></a>다음 단계 

- [Visual Studio용 Node.js 도구](https://github.com/Microsoft/nodejstools/wiki)에 대해 자세히 알아보기  
- [Visual Studio IDE](../ide/visual-studio-ide.md)에 대해 자세히 알아보기  