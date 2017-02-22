---
title: "프로파일링 도구 문제 해결 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0b61cdf7-75b7-4abd-aff2-7bd997717626
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 프로파일링 도구 문제 해결
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

프로파일링 도구를 사용할 때 다음 문제 중 하나가 발생할 수 있습니다.  
  
-   [프로파일링 도구에서 수집되는 데이터가 없음](#NoDataCollected)  
  
-   [성능 뷰 및 보고서에서 함수 이름에 번호가 표시됨](#NoSymbols)  
  
##  <a name="NoDataCollected"></a> 프로파일링 도구에서 수집되는 데이터가 없음  
 응용 프로그램을 프로파일링한 후에 프로파일링 데이터 파일\(.vsp\)이 만들어지지 않으며 출력 창이나 명령 창에 다음 경고가 표시됩니다.  
  
 PRF0025: 수집한 데이터가 없습니다.  
  
 이 문제는 다음과 같은 몇 가지 원인으로 발생할 수 있습니다.  
  
-   샘플링 또는 .NET 메모리 방법을 사용하여 프로파일링된 프로세스에서 자식 프로세스를 시작하며 이 프로세스가 응용 프로그램 작업을 수행하는 프로세스가 됩니다.  예를 들어 일부 응용 프로그램에서는 명령줄을 읽어 해당 응용 프로그램이 Windows 응용 프로그램으로 시작되었는지 또는 명령줄 응용 프로그램으로 시작되었는지를 확인합니다.  Windows 응용 프로그램이 요청된 경우 원래 프로세스에서 Windows 응용 프로그램으로 구성된 새 프로세스를 시작한 다음 원래 프로세스가 종료됩니다.  프로파일링 도구에서는 자식 프로세스의 데이터를 자동으로 수집하지 않으므로 이 경우 데이터가 수집되지 않습니다.  
  
     이러한 경우 프로파일링 데이터를 수집하려면 프로파일러를 사용하여 응용 프로그램을 시작하는 대신 프로파일러를 자식 프로세스에 연결합니다.  자세한 내용은 [방법: 실행 중인 프로세스에 프로파일러 연결 및 분리](../profiling/how-to-attach-and-detach-performance-tools-to-running-processes.md) 및 [Attach\(VSPerfCmd\)](../profiling/attach.md)를 참조하십시오.  
  
##  <a name="NoSymbols"></a> 성능 뷰 및 보고서에서 함수 이름에 번호가 표시됨  
 응용 프로그램을 프로파일링한 후 보고서 및 뷰에 함수 이름 대신 번호가 표시됩니다.  
  
 이 문제는 프로파일링 도구 분석 엔진에서 컴파일된 파일에 함수 이름 및 줄 번호 등의 소스 코드 정보를 매핑하는 기호 정보가 들어 있는 .pdb 파일을 찾을 수 없을 때 발생합니다.  기본적으로 컴파일러에서는 응용 프로그램 파일이 빌드될 때 .pdb 파일을 만듭니다.  .pdb 파일의 로컬 디렉터리에 대한 참조는 컴파일된 응용 프로그램에 저장됩니다.  분석 엔진에서는 .pdb 파일을 참조된 디렉터리에서 먼저 찾은 다음 현재 응용 프로그램 파일이 들어 있는 파일에서 찾습니다.  .pdb 파일을 찾을 수 없으면 분석 엔진에서는 함수 이름 대신 함수 오프셋을 사용합니다.  
  
 이 문제는 다음 두 가지 방법 중 하나로 해결할 수 있습니다.  
  
-   .pdb 파일을 찾아서 응용 프로그램 파일과 동일한 디렉터리에 배치합니다.  
  
-   프로파일링 데이터 파일\(.vsp\)에 기호 정보를 포함합니다.  자세한 내용은 [프로파일링 데이터 파일을 사용하여 기호 정보 저장](../profiling/saving-symbol-information-with-performance-data-files.md)을 참조하십시오.  
  
> [!NOTE]
>  분석 엔진을 사용하려면 .pdb 파일이 컴파일된 응용 프로그램 파일과 동일한 버전이어야 합니다.  응용 프로그램 파일의 이전 또는 이후 빌드에서 생성된 .pdb 파일은 작동하지 않습니다.