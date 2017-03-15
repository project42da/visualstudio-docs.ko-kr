---
title: "방법: 명령줄에서 기호 파일 위치 지정 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8aa067bb-e8bf-4081-aff0-cfbcf65934a0
caps.latest.revision: 11
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 11
---
# 방법: 명령줄에서 기호 파일 위치 지정
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

함수 이름 및 줄 번호와 같은 기호 정보를 표시하려면 VSPerfReport 명령줄 도구에서 프로파일링된 구성 요소의 기호 파일\(.pdb\)과 Windows 시스템 파일에 액세스해야 합니다.  기호 파일은 구성 요소가 컴파일될 때 만들어집니다.  자세한 내용은 [VSPerfReport](../profiling/vsperfreport.md)을 참조하십시오.  VSPerfReport에서는 다음과 같은 기호 파일의 위치를 자동으로 검색합니다.  
  
-   **\/SymbolPath** 옵션 또는 **\_NT\_SYMBOL\_PATH** 환경 변수에 지정된 경로  
  
-   구성 요소가 컴파일된 로컬 경로  
  
-   프로파일링 데이터 파일\(.vsp 또는 .vsps\)이 들어 있는 디렉터리  
  
 Microsoft에서는 많은 제품에 대한 .pdb 파일을 기호 서버에서 온라인으로 제공합니다.  보고에 사용 중인 컴퓨터가 인터넷에 연결되어 있으면 VSPerfReport에서는 이 온라인 기호 서버에 연결하여 자동으로 기호 정보를 찾고 해당 파일을 로컬 저장소에 저장합니다.  
  
 다음과 같은 방법으로 기호 파일 및 Microsoft 기호 서버 저장소의 위치를 지정할 수 있습니다.  
  
-   **\_NT\_SYMBOL\_PATH** 환경 변수를 설정합니다.  
  
-   VSPerfReport 명령줄에 **\/SymbolPath** 옵션을 추가합니다.  
  
 이 두 방법을 모두 사용할 수도 있습니다.  
  
> [!NOTE]
>  [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]가 로컬 컴퓨터에 설치되어 있는 경우에는 Windows 기호 파일의 위치가 이미 지정되어 있을 수 있습니다.  자세한 내용은 [방법: Windows 기호 정보 참조](../profiling/how-to-reference-windows-symbol-information.md)을 참조하십시오.  자세한 내용은 다음을 참조하십시오. 이 항목의 뒷부분에서 설명된 대로 위치 및 서버를 사용하려면 여전히 VSPerfReport를 구성해야 합니다.  
  
## Windows 기호 파일 지정  
  
#### Windows 기호 서버를 사용하도록 구성하려면  
  
1.  필요한 경우 기호 파일을 저장할 로컬 디렉터리를 만듭니다.  
  
2.  다음 구문을 사용하여 **\_NT\_SYMBOL\_PATH** 환경 변수나 VSPerfReport \/SymbolPath 옵션을 설정합니다.  
  
     **srv\*** *LocalStore* **\*http:\/\/msdl.microsoft.com\/downloads\/symbols**  
  
     여기서 *LocalStoreLocalStore*는 앞에서 만든 로컬 디렉터리의 경로입니다.  
  
## 구성 요소 기호 파일 지정  
 프로파일링 도구에서는 프로파일링할 구성 요소에 저장된 원래 위치나 프로파일링 데이터 파일이 들어 있는 폴더에서 해당 구성 요소의 .pdb 파일을 검색합니다.  **\_NT\_SYMBOL\_PATH** 또는 **\/SymbolPath** 옵션에 하나 이상의 경로를 추가하여 검색할 다른 위치를 지정할 수도 있습니다.  경로는 세미콜론으로 구분합니다.  
  
## 예제  
 다음 명령줄에서는 **\_NT\_SYMBOL\_PATH** 환경 변수를 Windows 기호 서버로 설정하고 로컬 디렉터리를 **C:\\Symbols**로 설정합니다.  
  
 **set  \_NT\_SYMBOL\_PATH\=srv\*C:\\symbols\*http:\/\/msdl.microsoft.com\/downloads\/symbols**  
  
 다음 VSPerfReport 명령줄에서는 **\/SymbolPath** 옵션을 사용하여 검색 경로에 C:\\Projects\\Symbols 디렉터리를 추가합니다.  
  
 **VSPerfReport**  *MyApp* **.exe \/SymbolPath:C:\\Projects\\Symbols \/summary:all**