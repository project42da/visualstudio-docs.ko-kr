---
title: 편집기 항목 템플릿을 사용 하 여 확장을 만들기 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], new - extensions
ms.assetid: fa3b993b-ab95-47fa-a38b-b788f3a5b2d8
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 9fd58c1ada38f8d79402bb08564bf91de23fb086
ms.sourcegitcommit: fe5a72bc4c291500f0bf4d6e0778107eb8c905f5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="creating-an-extension-with-an-editor-item-template"></a>편집기 항목 템플릿을 사용 하 여 확장 만들기
편집기 분류자, 장식 및 안쪽 여백을 추가 된 기본 편집기 확장을 만드는 Visual Studio SDK에 포함 된 항목 템플릿을 사용할 수 있습니다. 편집기 항목 템플릿은 Visual C# 또는 Visual Basic VSIX 프로젝트에 사용할 수 있습니다.  
  
## <a name="prerequisites"></a>전제 조건  
 Visual Studio 2015를 시작 하면 설치 하지 마십시오 Visual Studio SDK 다운로드 센터에서. Visual Studio 설치 프로그램에서 선택적 기능으로 포함 됩니다. 또한 VS SDK를 나중에 설치할 수 있습니다. 자세한 내용은 참조 [Visual Studio SDK 설치](../extensibility/installing-the-visual-studio-sdk.md)합니다.  
  
## <a name="creating-a-classifier-extension"></a>분류자 확장 만들기  
 편집기 분류자 항목 템플릿은 적절 한 텍스트 색을 지정 하는 편집기 분류자를 만듭니다 (이 경우 모든 항목)에서 모든 텍스트 파일입니다.  
  
1.  에 **새 프로젝트** 대화 상자에서 **Visual C#** 또는 **Visual Basic** 클릭 하 고 **확장성**합니다. 에 **템플릿** 창 선택 **VSIX 프로젝트**합니다. **이름** 상자에 `TestClassifier`을 입력합니다. **확인**을 클릭합니다.  
  
2.  에 **솔루션 탐색기**프로젝트 노드를 마우스 오른쪽 단추로 클릭 하 고 선택 **추가 / 새 항목**합니다. 이동에 Visual C# **확장성** 노드 선택한 **편집기 분류자**합니다. 기본 파일 이름 (EditorClassifier1.cs)을 그대로 둡니다.  
  
3.  세 개의 코드 파일은 다음과 같습니다.  
  
    -   EditorClassifier1.cs 포함는 `EditorClassifier1` 클래스입니다.  
  
    -   EditorClassifier1ClassificationDefinition.cs 포함는 `EditorClassifier1ClassificationDefinition` 클래스입니다.  
  
    -   EditorClassifier1Format.cs 포함는 `EditorClassifier1Format` 클래스입니다.  
  
    -   EditorClassifier1Provider.cs 포함는 `EditorClassifier1Provider` 클래스입니다.  
  
4.  프로젝트를 빌드하고 디버깅을 시작합니다. Visual Studio의 실험적 인스턴스가 표시 됩니다.  
  
     텍스트 파일을 열면 보라색 배경에 대 한 모든 텍스트 밑줄이 표시 됩니다.  
  
## <a name="creating-a-text-relative-adornment-extension"></a>상대 텍스트 장식 확장 만들기  
 편집기 텍스트 장식 템플릿은 만듭니다 텍스트 문자의 모든 인스턴스를 장식 하는 상대 텍스트 장식 빨간색 개요와 파란색 배경이 있는 상자를 사용 하 여 ' a'입니다. 텍스트 상대 되었기 때문에 상자 오버레이 'a' 문자를 이동 되거나 다시 포맷 하는 경우에 항상 합니다.  
  
1.  에 **새 프로젝트** 대화 상자에서 **Visual C#** 또는 **Visual Basic** 클릭 하 고 **확장성**합니다. 에 **템플릿** 창 선택 **VSIX 프로젝트**합니다. **이름** 상자에 `TestAdornment`을 입력합니다. **확인**을 클릭합니다.  
  
2.  에 **솔루션 탐색기**프로젝트 노드를 마우스 오른쪽 단추로 클릭 하 고 선택 **추가 / 새 항목**합니다. 이동에 Visual C# **확장성** 노드 선택한 **편집기 텍스트 장식**합니다. 기본 파일 이름 (TextAdornment1.cs/vb)을 그대로 둡니다.  
  
3.  두 코드 파일은 다음과 같습니다.  
  
    -   TextAdornment1.cs 포함는 `TextAdornment1` 클래스입니다.  
  
    -   TextAdornment1TextViewCreationListener.cs 포함는 `TextAdornment1TextViewCreationListener` 클래스입니다.  
  
4.  프로젝트를 빌드하고 디버깅을 시작합니다. 실험적 인스턴스가 표시 됩니다. 텍스트 파일을 열면 텍스트 'a' 문자는 빨간색 파란색 배경을 바탕으로 요약 되어 있습니다.  
  
## <a name="creating-a-viewport-relative-adornment-extension"></a>뷰포트에 상대적인 장식 확장 만들기  
 편집기 뷰포트 장식 템플릿은 보라색 상자 뷰포트의 오른쪽 위 모서리에 빨간색 개요를 추가 하는 뷰포트 상대 장식을 만듭니다.  
  
> [!NOTE]
>  *뷰포트* 현재 표시 되는 텍스트 보기의 영역입니다.  
  
#### <a name="to-create-a-viewport-adornment-extension-by-using-the-editor-viewport-adornment-template"></a>확장을 만들려면 뷰포트 장식 편집기 뷰포트 장식 템플릿을 사용 하 여  
  
1.  에 **새 프로젝트** 대화 상자에서 **Visual C#** 또는 **Visual Basic** 클릭 하 고 **확장성**합니다. 에 **템플릿** 창 선택 **VSIX 프로젝트**합니다. **이름** 상자에 `ViewportAdornment`을 입력합니다. **확인**을 클릭합니다.  
  
2.  에 **솔루션 탐색기**프로젝트 노드를 마우스 오른쪽 단추로 클릭 하 고 선택 **추가 / 새 항목**합니다. 이동에 Visual C# **확장성** 노드 선택한 **편집기 뷰포트 장식**합니다. 기본 파일 이름 (ViewportAdornment1.cs/vb)을 그대로 둡니다.  
  
3.  두 코드 파일은 다음과 같습니다.  
  
    -   ViewportAdornment1.cs 포함는 `ViewportAdornment1` 클래스입니다.  
  
    -   ViewportAdornment1TextViewCreationListener.cs 포함는 `ViewportAdornment1TextViewCreationListener` 클래스  
  
4.  프로젝트를 빌드하고 디버깅을 시작합니다. 실험적 인스턴스가 표시 됩니다. 새 텍스트 파일을 만드는 경우 빨간색 윤곽선이 있는 보라색 상자 뷰포트의 오른쪽 위 모퉁이에 표시 됩니다.  
  
## <a name="creating-a-margin-extension"></a>여백 확장 만들기  
 편집기 여백 템플릿은 만듭니다 단어 "Hello world!"와 함께 표시 되는 녹색 여백 가로 스크롤 막대 아래 합니다.  
  
#### <a name="to-create-a-margin-extension-by-using-the-editor-margin-template"></a>편집기 여백 서식 파일을 사용 하 여 여백 확장을 만들려면  
  
1.  에 **새 프로젝트** 대화 상자에서 **Visual C#** 또는 **Visual Basic** 클릭 하 고 **확장성**합니다. 에 **템플릿** 창 선택 **VSIX 프로젝트**합니다. **이름** 상자에 `MarginExtension`을 입력합니다. **확인**을 클릭합니다.  
  
2.  에 **솔루션 탐색기**프로젝트 노드를 마우스 오른쪽 단추로 클릭 하 고 선택 **추가 / 새 항목**합니다. 이동에 Visual C# **확장성** 노드 선택한 **편집기 여백**합니다. 기본 파일 이름 (EditorMargin1.cs/vb)을 그대로 둡니다.  
  
3.  두 코드 파일은 다음과 같습니다.  
  
    -   EditorMargin1.cs 포함는 `EditorMargin1` 클래스입니다.  
  
    -   EditorMargin1Factory.cs 포함는 `EditorMargin1Factory` 클래스입니다.  
  
4.  이 프로젝트를 빌드하고 디버깅을 시작 합니다. 실험적 인스턴스가 표시 됩니다. 텍스트 파일을 열면은 "Hello EditorMargin1" 라는 단어가 있는 녹색 여백 가로 스크롤 막대 아래에 표시 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [언어 서비스 및 편집기 확장 지점](../extensibility/language-service-and-editor-extension-points.md)