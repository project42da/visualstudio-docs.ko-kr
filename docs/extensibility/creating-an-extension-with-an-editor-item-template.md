---
title: "편집기 항목 템플릿을 사용 하 여 확장 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "편집기 [Visual Studio SDK] 새-확장"
ms.assetid: fa3b993b-ab95-47fa-a38b-b788f3a5b2d8
caps.latest.revision: 16
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 16
---
# 편집기 항목 템플릿을 사용 하 여 확장 만들기
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

편집기에 분류자, 장식 및 안쪽 여백을 추가 하는 기본 편집기 확장을 만들려면 Visual Studio SDK에 포함 된 항목 템플릿을 사용할 수 있습니다. 편집기 항목 템플릿은 Visual C\# 또는 Visual Basic VSIX 프로젝트에 사용할 수 있습니다.  
  
## 필수 구성 요소  
 Visual Studio 2015를 시작 하면 설치 하지 마십시오 Visual Studio SDK 다운로드 센터에서. Visual Studio 설치 프로그램의 선택적 기능으로 포함 됩니다. 또한 VS SDK를 나중에 설치할 수 있습니다. 자세한 내용은 [Visual Studio SDK 설치](../extensibility/installing-the-visual-studio-sdk.md)을 참조하십시오.  
  
## 분류자 확장 만들기  
 편집기 분류자 항목 템플릿은 적절 한 텍스트 색 지정 하는 편집기 분류자를 만듭니다 \(이 경우 모든 항목\)는 모든 텍스트 파일에서입니다.  
  
1.  에 **새 프로젝트** 대화 상자에서 **Visual C\#** 또는 **Visual Basic** 클릭 하 고 **확장성**합니다. 에 **템플릿** 창 **VSIX 프로젝트**합니다. 에 **이름** 상자에 입력 합니다 `TestClassifier`합니다.**확인**을 클릭합니다.  
  
2.  에 **솔루션 탐색기**, 프로젝트 노드를 마우스 오른쪽 단추로 클릭 하 고 선택 **추가 \/ 새 항목**합니다. 이동 하는 Visual C\# **확장성** 노드 선택한 **편집기 분류자**합니다. 기본 파일 이름 \(EditorClassifier1.cs\)을 그대로 둡니다.  
  
3.  코드 파일 세 개는 다음과 같습니다.  
  
    -   EditorClassifier1.cs 포함 된 `EditorClassifier1` 클래스입니다.  
  
    -   EditorClassifier1ClassificationDefinition.cs 포함 된 `OEditorClassifier1ClassificationDefinition` 클래스입니다.  
  
    -   EditorClassifier1Format.cs 포함 된 `EditorClassifier1Format`  클래스입니다.  
  
    -   EditorClassifier1Provider.cs 포함 된 `EditorClassifier1Provider` 클래스입니다.  
  
4.  프로젝트를 빌드하고 디버깅을 시작합니다. Visual Studio의 실험적 인스턴스가 표시 됩니다.  
  
     텍스트 파일을 열면 모든 텍스트는 보라색 배경과 밑줄이 표시 됩니다.  
  
## 상대 텍스트 장식 확장 만들기  
 편집기 텍스트 장식 템플릿에서 텍스트 문자의 모든 인스턴스가 데코 레이트 하는 상대 텍스트 장식 된 빨간색 개요와 파란색 배경을 상자를 사용 하 여 ' a'입니다. 텍스트에 상대적인 이기 때문에 상자 오버레이 'a' 문자를 이동 하거나 다시 포맷 하는 경우에 항상 합니다.  
  
1.  에 **새 프로젝트** 대화 상자에서 **Visual C\#** 또는 **Visual Basic** 클릭 하 고 **확장성**합니다. 에 **템플릿** 창 **VSIX 프로젝트**합니다. 에 **이름** 상자에 입력 합니다 `TestAdornment`합니다.**확인**을 클릭합니다.  
  
2.  에 **솔루션 탐색기**, 프로젝트 노드를 마우스 오른쪽 단추로 클릭 하 고 선택 **추가 \/ 새 항목**합니다. 이동 하는 Visual C\# **확장성** 노드 선택한 **편집기 텍스트 장식**합니다. 기본 파일 이름 \(TextAdornment1.cs\/vb\)을 그대로 둡니다.  
  
3.  코드 파일 두 개는 다음과 같습니다.  
  
    -   TextAdornment1.cs 포함 된 `TextAdornment1` 클래스입니다.  
  
    -   extAdornment1TextViewCreationListener.cs 포함 된 `TextAdornment1TextViewCreationListener` 클래스입니다.  
  
4.  프로젝트를 빌드하고 디버깅을 시작합니다. 실험적 인스턴스가 표시 됩니다. 텍스트 파일을 열면 텍스트 'a' 문자는 파란색 배경과 빨간색으로 요약 되어 있습니다.  
  
## 뷰포트에 상대적인 장식 확장 만들기  
 편집기 뷰포트 장식 템플릿은 뷰포트의 오른쪽 위 모서리에 빨간색 윤곽선이 있는 보라색 상자를 추가 하는 뷰포트 상대 장식을 만듭니다.  
  
> [!NOTE]
>  *뷰포트* 텍스트 뷰가 현재 표시 되는 영역입니다.  
  
#### 확장을 만들려면 뷰포트 장식 편집기 뷰포트 장식 템플릿을 사용 하 여  
  
1.  에 **새 프로젝트** 대화 상자에서 **Visual C\#** 또는 **Visual Basic** 클릭 하 고 **확장성**합니다. 에 **템플릿** 창 **VSIX 프로젝트**합니다. 에 **이름** 상자에 입력 합니다 `ViewportAdornment`합니다.**확인**을 클릭합니다.  
  
2.  에 **솔루션 탐색기**, 프로젝트 노드를 마우스 오른쪽 단추로 클릭 하 고 선택 **추가 \/ 새 항목**합니다. 이동 하는 Visual C\# **확장성** 노드 선택한 **편집기 뷰포트 장식**합니다. 기본 파일 이름 \(ViewportAdornment1.cs\/vb\)을 그대로 둡니다.  
  
3.  코드 파일 두 개는 다음과 같습니다.  
  
    -   ViewportAdornment1.cs 포함 된 `ViewportAdornment1` 클래스입니다.  
  
    -   ViewportAdornment1TextViewCreationListener.cs 포함 된 `ViewportAdornment1TextViewCreationListener` 클래스  
  
4.  프로젝트를 빌드하고 디버깅을 시작합니다. 실험적 인스턴스가 표시 됩니다. 새 텍스트 파일을 만드는 경우 빨간색 윤곽선이 있는 보라색 상자 뷰포트의 오른쪽 위 모퉁이에 표시 됩니다.  
  
## 여백 확장 만들기  
 편집기 여백을 템플릿에서 단어 "Hello world\!"와 함께 표시 되는 녹색 여백 가로 스크롤 막대 아래입니다.  
  
#### 편집기 여백을 서식 파일을 사용 하 여 여백 확장을 만들려면  
  
1.  에 **새 프로젝트** 대화 상자에서 **Visual C\#** 또는 **Visual Basic** 클릭 하 고 **확장성**합니다. 에 **템플릿** 창 **VSIX 프로젝트**합니다. 에 **이름** 상자에 입력 합니다 `MarginExtension`합니다.**확인**을 클릭합니다.  
  
2.  에 **솔루션 탐색기**, 프로젝트 노드를 마우스 오른쪽 단추로 클릭 하 고 선택 **추가 \/ 새 항목**합니다. 이동 하는 Visual C\# **확장성** 노드 선택한 **편집기 뷰포트 장식**합니다. 기본 파일 이름 \(EditorMargin1.cs\/vb\)을 그대로 둡니다.  
  
3.  코드 파일 두 개는 다음과 같습니다.  
  
    -   EditorMargin1.cs 포함 된 `EditorMargin1` 클래스입니다.  
  
    -   EditorMargin1Factory.cs 포함 된 `EditorMargin1Factory` 클래스입니다.  
  
4.  이 프로젝트를 빌드하고 디버깅을 시작 합니다. 실험적 인스턴스가 표시 됩니다. 텍스트 파일을 열면은 "Hello EditorMargin1" 라는 단어가 있는 녹색 여백 가로 스크롤 막대 아래에 표시 됩니다.  
  
## 참고 항목  
 [언어 서비스 및 편집기 확장 지점](../extensibility/language-service-and-editor-extension-points.md)