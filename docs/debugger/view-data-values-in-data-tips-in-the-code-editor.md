---
title: "코드 편집기에서 데이터 팁의 데이터 값 보기 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "FSharp"
  - "VB"
  - "CSharp"
  - "C++"
  - "JScript"
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "DataTips 도구"
  - "디버깅[Visual Studio], DataTips"
ms.assetid: ffa7bd18-439b-4685-a9b3-c7884b5de41f
caps.latest.revision: 38
caps.handback.revision: 38
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 코드 편집기에서 데이터 팁의 데이터 값 보기
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

DataTips를 통해 디버깅하는 동안 프로그램의 변수에 대한 정보를 손쉽게 볼 수 있습니다.  DataTips는 중단 모드에서 현재 실행 범위 내의 변수에 대해서만 작동합니다.  
  
 [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)]에서는 DataTips를 소스 파일의 특정 위치에 고정하거나 모든 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 창의 맨 위에 배치할 수 있습니다.  
  
### DataTip을 표시하려면\(중단 모드에서만\)  
  
1.  소스 창에서 현재 범위에 있는 변수 위에 마우스 포인터를 놓습니다.  
  
     DataTips가 나타납니다.  
  
    > [!NOTE]
    >  DataTip은 커서가 가리키고 있는 컨텍스트가 아니라 실행이 일시 중단된 컨텍스트에서 항상 평가됩니다.  현재 컨텍스트에 있는 변수와 이름이 같은 또 다른 함수의 변수를 가리키는 경우 다른 함수의 변수 값이 현재 컨텍스트의 변수 값으로 표시됩니다.  
  
2.  마우스 포인터를 제거하면 DataTip이 사라집니다.  DataTip을 고정하여 열어 두려면 **소스에 고정** 아이콘을 클릭합니다.  
  
    -   변수를 마우스 오른쪽 단추로 클릭하고 **소스에 고정**을 클릭합니다.  
  
     고정된 DataTip은 디버깅 세션이 종료될 때 닫힙니다.  
  
### DataTip의 고정을 해제하고 다른 위치에 배치하려면  
  
-   고정된 DataTip에서 **소스에서 고정 해제** 아이콘을 클릭합니다.  
  
     고정 아이콘이 고정 해제된 위치로 변경됩니다.  이제 DataTip이 열린 창 위에 배치됩니다.  부동 DataTip은 디버깅 세션이 종료될 때 닫힙니다.  
  
### 부동 DataTip을 다시 고정하려면  
  
-   DataTip에서 고정 아이콘을 클릭합니다.  
  
     고정 아이콘이 고정된 위치로 바뀝니다.  DataTip이 소스 창 밖에 있으면 고정 아이콘을 사용할 수 없으며 DataTip을 고정할 수 없습니다.  
  
### DataTip을 닫으려면  
  
-   마우스 포인터를 DataTip 위에 놓고 **닫기** 아이콘을 클릭합니다.  
  
### 모든 DataTips를 닫으려면  
  
-   **디버그** 메뉴에서 **모든 DataTips 지우기**를 클릭합니다.  
  
### 특정 파일에 대한 모든 DataTips를 닫으려면  
  
-   **디버그** 메뉴에서 *File***에 고정된 모든 DataTips 지우기**를 클릭합니다.  
  
## 정보 확장 및 편집  
 DataTips를 사용하면 배열, 구조체 또는 개체를 확장하여 해당 멤버를 볼 수 있습니다.  DataTips에서 변수 값을 편집할 수도 있습니다.  
  
#### 변수를 확장하여 해당 요소를 보려면  
  
-   DataTip에서 변수 이름 앞의 **\+** 부호 위에 마우스 포인터를 놓습니다.  
  
     변수가 확장되어 해당 요소가 트리 형태로 표시됩니다.  
  
     변수가 확장되면 키보드의 화살표 키를 사용하여 위아래로 이동할 수 있습니다.  또는 마우스를 사용할 수 있습니다.  
  
#### DataTip을 사용하여 변수 값을 편집하려면  
  
1.  DataTip에서 값을 클릭합니다.  읽기 전용 값에는 사용할 수 없습니다.  
  
2.  새 값을 입력하고 Enter 키를 누릅니다.  
  
## DataTips 투명하게 만들기  
 DataTip 뒤에 있는 코드를 보려면 DataTip을 임시로 투명하게 만듭니다.  고정 또는 부동 DataTips에는 적용되지 않습니다.  
  
#### DataTips를 투명하게 만들려면  
  
-   DataTip에서 Ctrl 키를 누릅니다.  
  
     Ctrl 키를 누르고 있는 동안에는 DataTip이 투명한 상태로 유지됩니다.  
  
## 복잡한 데이터 형식 시각화  
 DataTips의 변수 이름 옆에 돋보기 아이콘이 나타나는 경우 해당 데이터 형식의 변수에 [시각화 도우미](../debugger/create-custom-visualizers-of-data.md)를 하나 이상 사용할 수 있습니다.  시각화 도우미를 사용하면 정보를 더 의미 있는 방식\(대개 그래픽 방식\)으로 표시할 수 있습니다.  
  
#### 시각화 도우미를 사용하여 변수의 내용을 보려면  
  
-   돋보기 아이콘을 클릭하고 데이터 형식에 대한 기본 시각화 도우미를 선택합니다.  
  
     또는  
  
     시각화 도우미 옆의 팝업 화살표를 클릭하고 시각화 도우미 목록에서 데이터 형식에 적절한 시각화 도우미를 선택합니다.  
  
     시각화 도우미가 정보를 표시합니다.  
  
## 조사식 창에 정보 추가  
 변수를 계속 조사하려면 DataTip에서 **조사식** 창에 변수를 추가합니다.  
  
#### 조사식 창에 변수를 추가하려면  
  
-   DataTip을 오른쪽 단추로 클릭하고 **조사식 추가**를 클릭합니다.  
  
     변수가 **조사식** 창에 추가됩니다.  여러 **조사식** 창을 지원하는 버전을 사용하는 경우에는 변수가 **조사식 1**에 추가됩니다.  
  
## DataTips 가져오기 및 내보내기  
 DataTips를 XML 파일로 내보내서 동료와 공유하거나 텍스트 편집기를 사용하여 편집할 수 있습니다.  
  
#### DataTips를 내보내려면  
  
1.  디버그 메뉴에서 **DataTips 내보내기**를 클릭합니다.  
  
     **DataTips 내보내기** 대화 상자가 나타납니다.  
  
2.  표준 파일 기술을 사용하여 XML 파일을 저장할 위치로 이동하고 **파일 이름** 상자에 파일 이름을 입력한 다음 **확인**을 클릭합니다.  
  
#### DataTips를 가져오려면  
  
1.  디버그 메뉴에서 **DataTips 가져오기**를 클릭합니다.  
  
     **DataTips 가져오기** 대화 상자가 나타납니다.  
  
2.  이 대화 상자에서 열려는 XML 파일을 찾고 **확인**을 클릭합니다.  
  
## 참고 항목  
 [디버거에서 데이터 보기](../debugger/viewing-data-in-the-debugger.md)   
 [방법: 간략한 조사식 대화 상자 사용](../Topic/How%20to:%20Use%20the%20QuickWatch%20Dialog%20Box.md)   
 [시각화 도우미](../debugger/create-custom-visualizers-of-data.md)   
 [방법: 디버거 창의 숫자 형식 변경](../Topic/How%20to:%20Change%20the%20Numeric%20Format%20of%20Debugger%20Windows.md)