---
title: "예외 문제 해결: Cordova 빌드 오류 | Microsoft Docs"
ms.custom: ""
ms.date: "11/03/2016"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "BLD102"
  - "BLD10205"
  - "BLD301"
  - "BLD401"
  - "BLDErr_Build_NodeMissing"
  - "BLDErr_BLD_Win8Required"
ms.assetid: 781c09e3-0704-4b30-9230-036cbdb2dff9
caps.latest.revision: 14
caps.handback.revision: 14
author: "mikejo5000"
ms.author: "mikejo"
---
# 예외 문제 해결: Cordova 빌드 오류
이 항목에서는 Apache Cordova용 도구 Visual Studio를 사용할 때 표시될 수 있는 몇 가지 일반적인 오류 메시지에 대해 설명합니다.  
  
-   [MSBUILD: cordova 빌드 오류 BLD102: 해당 파일 또는 디렉터리 없음('config.xml')](#BLD102)  
  
-   [MSBUILD: cordova 빌드 오류 BLD301: 원격 iOS 빌드 에이전트가 구성되지 않았습니다.](#BLD301)  
  
-   [MSBUILD: cordova 빌드 오류 BLD401: &lt;모듈 이름&gt; 모듈을 찾을 수 없습니다.](#BLD401)  
  
-   [MSBUILD: Cordova 빌드 오류 BLD10205: Android 대상을 설치하세요.](#BLD10205)  
  
-   [BLDErr_Build_NodeMissing Node.js 실행 파일의 경로를 파악할 수 없습니다.](#BLDErr_Build_NodeMissing)  
  
-   [BLDErr_Build_Win8Required](#BLDErr_Build_Win8Required)  
  
 Cordova 앱의 오류 문제를 해결하는 데 보다 일반적인 도움이 필요하면, [Resolving build errors](https://taco.visualstudio.com/en-us/docs/resolving-build-errors/)\(빌드 오류 해결\)를 참조하세요.  
  
##  <a name="BLD102"></a> MSBUILD: cordova 빌드 오류 BLD102: 해당 파일 또는 디렉터리 없음\('config.xml'\)  
 이 오류가 표시되는 경우 프로젝트의 프로젝트 루트에 config.xml 파일이 있는지 확인하고, 프로젝트가 네트워크 공유가 아니라 로컬 컴퓨터에 있는지 확인합니다.  
  
 자세한 내용은 이 [StackOverflow 게시물](http://stackoverflow.com/questions/27134007/new-cordova-project-gives-the-error-bld00102-no-such-file-or-directory-confi)을 참조하세요.  
  
##  <a name="BLD301"></a> MSBUILD: cordova 빌드 오류 BLD301: 원격 iOS 빌드 에이전트가 구성되지 않았습니다.  
 전체 오류 문자열은 다음과 같습니다.  
  
-   MSBUILD: cordova 빌드 오류 BLD301: 원격 iOS 빌드 에이전트가 구성되지 않았습니다. 도구 \> 옵션 \> Apache Cordova용 도구 \> 원격 에이전트 구성에서 원격 iOS 빌드 에이전트를 구성하세요. 자세한 내용 및 대안은 http:\/\/go.microsoft.com\/fwlink\/?LinkID\=511904를 참조하세요.  
  
 iOS용 원격 빌드 에이전트를 설치 및 구성하는 방법에 대한 자세한 내용은 [iOS 설치 가이드](http://taco.visualstudio.com/en-us/docs/ios-guide/)를 참조하세요.  
  
##  <a name="BLD401"></a> MSBUILD: cordova 빌드 오류 BLD401: \<모듈 이름\> 모듈을 찾을 수 없습니다.  
 전체 오류 문자열은 다음과 같습니다.  
  
-   MSBUILD: cordova 빌드 오류 BLD401: 오류: BLD00401: \<모듈 이름\> 모듈을 찾을 수 없습니다. 도구 \-\-\> 옵션 \-\-\> Apache Cordova용 도구 \-\-\> Cordova 도구 \-\-\> Cordova 캐시 지우기로 이동하여 다시 빌드해 보세요.  
  
 캐시를 지우고 vs\-tac를 다시 설치해야 할 수도 있습니다. 자세한 내용은 [vs\-tac 다시 설치](http://taco.visualstudio.com/en-us/docs/configure-vs-tools-apache-cordova#vstac)를 참조하세요.  
  
 캐시를 지운 후에 프로젝트의 플랫폼 폴더를 삭제합니다. 그런 다음 빌드를 다시 시도합니다.  
  
##  <a name="BLD10205"></a> MSBUILD: Cordova 빌드 오류 BLD10205: Android 대상을 설치하세요.  
 이 오류가 표시되는 경우 Android SDK Manager\(SDK Manager.exe\)를 사용하여 선택한 대상 장치에 대한 필수 종속성을 설치해야 합니다.  
  
 필수 API 수준 및 다른 Android SDK 구성 요소에 대한 자세한 내용은 [수동으로 종속성 설치](http://taco.visualstudio.com/en-us/docs/configure-vs-tools-apache-cordova#ThirdParty)를 참조하세요.  
  
 또한 Visual Studio에서 Android SDK를 찾는 데 사용하는 위치를 확인해야 합니다. 이렇게 하려면 [시스템 환경 변수 재정의](http://taco.visualstudio.com/en-us/docs/configure-vs-tools-apache-cordova#env-var)를 참조하세요.  
  
 도구를 사용하는 데 필요한 구성 요소를 설치하는 방법에 대한 자세한 내용은 [타사 도구](http://taco.visualstudio.com/en-us/docs/install-vs-tools-apache-cordova#choose)를 참조하세요.  
  
##  <a name="BLDErr_Build_NodeMissing"></a> BLDErr\_Build\_NodeMissing Node.js 실행 파일의 경로를 파악할 수 없습니다.  
 Node.js가 기본 위치에 설치되지 않은 경우 Visual Studio에서 파일을 찾을 수 없습니다. Node.js를 기본 위치에 다시 설치합니다. 자세한 내용은 이 [StackOverflow 게시물](http://stackoverflow.com/questions/32203992/vs2015-cordova-apps-blderr-build-nodemissing)과 [안전하게 Node.js 업데이트](http://taco.visualstudio.com/en-us/docs/change-node-version/) 문서를 참조하세요.  
  
##  <a name="BLDErr_Build_Win8Required"></a> BLDErr\_Build\_Win8Required  
 Visual Studio Tools for Apache Cordova를 사용하여 만든 앱에서 Windows를 대상으로 하려면 Windows 8.1이 필요합니다.