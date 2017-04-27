---
title: "방법: 프로파일링 권한 설정 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "프로파일링, 권한 설정"
  - "보안[Visual Studio ALM], 권한 설정"
  - "권한[Visual Studio ALM], 프로파일링"
  - "프로파일링 도구, 프로파일링 권한 설정"
  - "성능 도구, 프로파일링 권한 설정"
ms.assetid: 69f27896-8f46-4ef3-bfb7-726d95304f3a
caps.latest.revision: 23
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 23
---
# 방법: 프로파일링 권한 설정
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 항목에서는 컴퓨터의 관리자가 프로파일링을 수행하는 데 필요한 보안 권한을 해당 컴퓨터에 대한 관리자 권한이 없는 사용자 또는 그룹에 할당하는 방법에 대해 설명합니다.  
  
 기본 보안 원칙에서는 응용 프로그램이 해당 응용 프로그램에 필요한 권한만 사용하여 실행되도록 합니다.  이 원칙은 사용자에게도 적용됩니다.  사용자가 관리자 그룹의 멤버가 아니라 사용자 그룹의 멤버로 로그온하더라도 필요한 작업을 수행하는 데 아무런 문제가 없다면 해당 사용자에게 관리자 권한을 할당하지 말아야 합니다.  첫 번째 절차인 "사용자 권한이 있는 사용자 계정을 만들려면"에서는 사용자 그룹의 멤버에 대한 사용자 계정을 만드는 방법을 설명합니다.  
  
 **요구 사항**  
  
-   [!INCLUDE[vsUltLong](../code-quality/includes/vsultlong_md.md)], [!INCLUDE[vsPreLong](../code-quality/includes/vsprelong_md.md)], [!INCLUDE[vsPro](../code-quality/includes/vspro_md.md)]  
  
 사용자 그룹의 멤버는 팀의 다른 멤버와 공유하는 디스크상의 폴더 및 파일에 액세스할 수 있어야 합니다.  두 번째 절차인 "공유 프로젝트 파일에 대한 액세스 권한을 부여하려면"에서는 해당 액세스 권한을 부여하는 방법을 설명합니다.  
  
 사용자 그룹의 멤버는 관리자가 해당 사용자에게 프로파일링 도구의 소프트웨어 드라이버에 대한 액세스 권한을 부여한 경우 의 프로파일링 도구를 실행할 수 있습니다.  마지막 절차인 "프로파일링 드라이버에 대한 액세스 권한을 부여하려면"에서는 해당 드라이버에 대한 액세스 권한을 부여하는 방법을 설명합니다.  
  
> [!NOTE]
>  이러한 절차의 단계를 수행하려면 관리자 권한이 있어야 합니다.  
  
### 사용자 권한이 있는 사용자 계정을 만들려면  
  
1.  **내 컴퓨터**를 마우스 오른쪽 단추로 클릭한 다음 **관리**를 클릭합니다.  
  
     **컴퓨터 관리** 창이 열립니다.  
  
2.  **로컬 사용자 및 그룹**을 확장합니다.  
  
3.  **사용자** 폴더를 마우스 오른쪽 단추로 클릭한 다음 **새 사용자**를 클릭합니다.  
  
     **새 사용자** 대화 상자가 나타납니다.  
  
4.  현재 만들고 있는 사용자 계정에 대한 정보를 이 대화 상자의 필드에 입력합니다.  암호를 지정합니다.  필요한 경우, 다음에 로그온할 때 사용자가 암호를 변경하도록 하는 확인란을 선택합니다.  
  
5.  **만들기**를 클릭한 다음 **닫기**를 클릭합니다.  
  
     관리자 권한이 없는 사용자의 그룹인 사용자 그룹에 새 사용자가 나타납니다.  
  
### 공유 프로젝트 파일에 대한 액세스 권한을 부여하려면  
  
1.  Windows 탐색기에서, \(또는 File Explorer\) 사용자가 사용하고 프로젝트 팀에서 공유하는 프로젝트 파일에 대한 폴더 트리의 루트를 찾습니다.  
  
     이 폴더의 경로는 다음과 비슷합니다.  
  
    ```  
    D:\ourProject  
    ```  
  
2.  이 폴더를 마우스 오른쪽 단추로 클릭한 다음 **속성**을 클릭합니다.  
  
     **\<folder name\> 속성** 대화 상자가 나타납니다.  
  
3.  **보안** 탭을 클릭합니다.  
  
4.  **그룹 또는 사용자 이름** 상자에서 사용자 계정의 이름을 클릭합니다.  
  
5.  **\<user name\>**의 사용 권한 상자에서 **모든 권한** 확인란을 선택합니다.  
  
6.  **확인**을 클릭합니다.  
  
     이렇게 하면 5단계에서 선택한 폴더부터 공유 폴더 트리에 대한 권한이 사용자에게 부여됩니다.  
  
### 프로파일링 드라이버에 대한 액세스 권한을 부여하려면  
  
1.  관리자 권한으로 명령 프롬프트를 엽니다.  
  
2.  다음 디렉터리로 이동합니다.  
  
    ```  
    <drive>:\Program Files\Microsoft Visual Studio 10\Team Tools\Performance Tools  
    ```  
  
3.  다음 명령을 실행합니다.  
  
    ```  
    vsperfcmd /admin:driver,start /admin:service,start  
    ```  
  
     이 명령을 실행하면 프로파일링 도구의 드라이버가 설치 및 시작됩니다.  
  
     이 명령은 프로파일링 드라이버 및 서비스를 시작하여 관리자가 아닌 사용자가 자신의 사용자 프로세스 공간에서 프로파일링 기능을 사용할 수 있도록 합니다.  관리자만 이 명령을 실행할 수 있으므로 관리자가 아닌 사용자가 실행할 경우 명령이 실행되지 않습니다.  
  
     이 절차의 최종 단계를 수행하지 않으면 컴퓨터를 다시 시작한 후 이 단계의 효과가 취소됩니다.  
  
4.  컴퓨터에 대한 관리자 액세스 권한이 없는 사용자 또는 그룹이 프로파일링 드라이버 기능에 액세스할 수 있도록 하려면 다음 명령을 실행합니다.  
  
    ```  
    vsperfcmd /admin:security,allow,<right[,right],<user name|group name>  
    ```  
  
     이 명령을 실행하면 프로파일링 도구에 대한 액세스 권한이 \<user name\> 또는 \<group name\> 계정에 부여됩니다.  \<right\> 옵션에 따라 사용자가 액세스할 수 있는 프로파일링 기능이 결정됩니다.  이 \<right\> 옵션은 다음 값 중 하나 이상일 수 있습니다.  
  
    -   FullAccess – 서비스에서의 성능 데이터 수집, 샘플링 및 상호 세션 프로파일링을 포함하여 모든 프로파일링 방법에 액세스할 수 있습니다.  
  
    -   SampleProfiling – 샘플 프로파일링 방법에 액세스할 수 있습니다.  
  
    -   CrossSession – 프로파일링 서비스에 필요한 상호 세션 프로파일링에 액세스할 수 있습니다.  
  
5.  \(선택 사항\) 컴퓨터를 다시 시작한 뒤에도 이전 단계의 결과를 유지하려면 다음 명령을 실행합니다.  
  
    ```  
    vsperfcmd /admin:driver,autostart,on  
    ```  
  
 이제 지정된 사용자는 로그온한 후에 관리자 권한 없이도 프로파일링 도구를 사용할 수 있습니다.  
  
## 참고 항목  
 [성능 세션 구성](../profiling/configuring-performance-sessions.md)   
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [프로파일링 및 Windows Vista 보안](../profiling/profiling-and-windows-vista-security.md)