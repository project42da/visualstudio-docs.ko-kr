---
title: "방법: 특정 함수로 계측 제한 | Microsoft Docs"
ms.custom: ""
ms.date: "12/08/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "성능 도구, 함수로 계측 제한"
ms.assetid: bd98d6bf-2560-4eba-b063-2facb09f87c4
caps.latest.revision: 19
caps.handback.revision: 19
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 방법: 특정 함수로 계측 제한
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

**성능 세션**의 **고급** 페이지 또는 대상 이진 파일 속성 페이지의 옵션을 설정하여 계측 및 데이터 수집을 하나 이상의 함수로 제한할 수 있습니다.  
  
-   성능 세션 속성 페이지에 함수를 지정하는 경우 이러한 함수만 세션의 모든 계측된 이진 파일에서 계측됩니다.  
  
-   대상 이진 파일의 속성 페이지에 함수를 지정하는 경우 해당 이진 파일에 있는 함수만 계측됩니다.  성능 세션의 다른 이진 파일에 있는 함수는 평소처럼 계측됩니다.  
  
 이러한 데이터 수집 제한 방식은 계측 프로파일링 방법을 선택한 경우에만 지원됩니다.  
  
> [!NOTE]
>  또한 **성능 세션** 속성 페이지의 **고급** 페이지를 사용하여 프로파일링 도구의 [VSInstr](../profiling/vsinstr.md) 명령줄 계측 도구에서 사용할 수 있는 다른 옵션을 설정할 수도 있습니다.  
  
### 성능 세션의 특정 함수로 계측을 제한하려면  
  
1.  **성능 탐색기**에서 세션 이름을 마우스 오른쪽 단추로 클릭한 다음 **속성**을 클릭합니다.  
  
     **속성 페이지** 대화 상자가 표시됩니다.  
  
2.  **속성 페이지** 대화 상자에서 **고급**을 클릭합니다.  
  
3.  **추가 계측 옵션** 텍스트 상자에 다음 구문을 사용하여 계측할 함수의 이름을 입력합니다.  
  
     **\/include:** `FuncSpec` **\[;** `FuncSpec` **\]** `...`  
  
     `FuncSpec`은 네임스페이스 및 함수 이름으로,  형식은 `Namespace`**::**`FunctionName`입니다.  세미콜론을 사용하면 여러 함수를 구분할 수 있습니다  하나 이상의 문자에 대해 와일드카드를 지정하려면 별표\(\*\)를 사용합니다.  예를 들어 **\/include:MyNS::\*** 는 MyNS 네임스페이스의 모든 함수를 지정합니다.  
  
    > [!NOTE]
    >  이진 파일의 함수를 나열하려면 프로파일링 도구 설치 디렉터리\(대개 [!INCLUDE[vsprvsts](../code-quality/includes/vsprvsts_md.md)] 설치 디렉터리 아래의 \\Team Tools\\Performance Tools 디렉터리\)에서 명령 프롬프트 창을 열고 vsinstr \/DumpFuncs를 입력합니다.  
  
### 계측을 이진 파일의 특정 함수로 제한하려면  
  
1.  **성능 탐색기**에서 성능 세션의 **대상** 노드에 있는 이진 파일 이름을 찾습니다.  
  
2.  이진 파일 이름을 마우스 오른쪽 단추로 클릭한 다음 **속성**을 클릭합니다.  
  
     **속성 페이지** 대화 상자가 표시됩니다.  
  
3.  **속성 페이지** 대화 상자에서 **고급**을 클릭합니다.  
  
4.  **추가 계측 옵션** 텍스트 상자에 다음 구문을 사용하여 계측할 함수의 이름을 입력합니다.  
  
     **\/include:** `FuncSpec` **\[;** `FuncSpec` **\]** `...`  
  
     `FuncSpec` 은 네임스페이스 및 함수 이름으로,  형식은 `Namespace`**::**`FunctionName`입니다.  세미콜론을 사용하면 여러 함수를 구분할 수 있습니다  하나 이상의 문자에 대해 와일드카드를 지정하려면 별표\(\*\)를 사용합니다.  예를 들어 **\/include:MyNS::\*** 는 MyNS 네임스페이스의 모든 함수를 지정합니다.  
  
    > [!NOTE]
    >  이진 파일의 함수를 나열하려면 프로파일링 도구 설치 디렉터리\(대개 [!INCLUDE[vsprvsts](../code-quality/includes/vsprvsts_md.md)] 설치 디렉터리 아래의 \\Team Tools\\Performance Tools 디렉터리\)에서 명령 프롬프트 창을 열고 vsinstr \/DumpFuncs를 입력합니다.  
  
## 참고 항목  
 [데이터 수집 제어](../profiling/controlling-data-collection.md)   
 [방법: 계측을 특정 DLL로 제한](../profiling/how-to-limit-instrumentation-to-specific-dlls.md)   
 [방법: 추가 계측 옵션 지정](../Topic/How%20to:%20Specify%20Additional%20Instrumentation%20Options.md)