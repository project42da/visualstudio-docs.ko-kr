---
title: "ClickOnce 응용 프로그램 지역화 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-deployment"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "ClickOnce 배포, 요청 시 다운로드"
  - "ClickOnce 배포, 전역화"
  - "ClickOnce 배포, 지역화"
  - "콘솔 응용 프로그램, ClickOnce 응용 프로그램"
  - "응용 프로그램 배포[ClickOnce], ClickOnce 응용 프로그램 지역화"
  - "지역화, ClickOnce 배포"
  - "Windows Forms, ClickOnce 응용 프로그램"
  - "WPF, ClickOnce 응용 프로그램"
ms.assetid: c92b193b-054d-4923-834b-d4226a4c7a1a
caps.latest.revision: 16
caps.handback.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# ClickOnce 응용 프로그램 지역화
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

지역화는 응용 프로그램을 특정 문화권에 적합하게 만드는 프로세스입니다.  이 프로세스에서는 UI\(사용자 인터페이스\) 텍스트를 지역별 언어로 번역하고, 올바른 데이터 및 통화 형식 지정을 사용하고, 양식에서 컨트롤 크기를 조정하고, 필요하면 오른쪽에서 왼쪽으로 컨트롤을 미러링합니다.  
  
 응용 프로그램을 지역화하면 위성 어셈블리 하나 이상이 만들어집니다.  각 어셈블리에는 지정된 문화권과 관련된 UI 문자열, 이미지 및 기타 리소스가 포함됩니다.  응용 프로그램의 주 실행 파일에는 응용 프로그램의 기본 문화권에 대한 문자열이 포함됩니다.  
  
 이 항목에서는 다른 문화권에 맞게 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램을 배포하는 세 가지 방법을 설명합니다.  
  
-   모든 위성 어셈블리를 단일 배포에 포함합니다.  
  
-   각 문화권에 대해 각각 단일 위성 어셈블리가 포함된 하나의 배포를 생성합니다.  
  
-   요청 시 위성 어셈블리를 다운로드합니다.  
  
## 배포에 모든 위성 어셈블리 포함  
 여러 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 배포를 게시하지 않고 모든 위성 어셈블리를 포함하는 단일 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 배포를 게시할 수 있습니다.  
  
 이 메서드는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]의 기본값입니다.  [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서 이 메서드를 사용하려고 추가 작업을 수행할 필요는 없습니다.  
  
 이 메서드를 MageUI.exe와 함께 사용하려면 MageUI.exe에서 응용 프로그램의 문화권을 **중립**으로 설정해야 합니다.  그 후에 모든 위성 어셈블리를 배포에 수동으로 포함해야 합니다.  MageUI.exe에서 응용 프로그램 매니페스트의 **파일** 탭에서 **채우기** 단추를 사용하여 위성 어셈블리를 추가할 수 있습니다.  
  
 이 접근 방법의 장점은 단일 배포를 만들고 지역화된 배포 과정을 단순화한다는 점입니다.  런타임에 사용자 Windows 운영 체제의 기본 문화권에 따라 해당 위성 어셈블리가 사용됩니다.  이 접근 방법의 단점은 클라이언트 컴퓨터에서 응용 프로그램이 설치되거나 업데이트될 때마다 모든 위성 어셈블리를 다운로드한다는 점입니다.  응용 프로그램에 많은 문자열이 포함되거나 고객의 네트워크 연결 속도가 느리면 응용 프로그램 업데이트 중에 이 프로세스가 성능에 영향을 미칠 수 있습니다.  
  
> [!NOTE]
>  이 접근 방법에서는 응용 프로그램이 컨트롤의 높이, 너비 및 위치를 다양한 문화권의 다양한 텍스트 문자열 크기에 맞게 자동으로 조정한다고 가정합니다.  Windows Forms에는 <xref:System.Windows.Forms.FlowLayoutPanel> 및 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤과 <xref:System.Windows.Forms.Control.AutoSize%2A> 속성을 포함하여 양식을 쉽게 지역화할 수 있도록 디자인하는 데 사용되는 다양한 컨트롤 및 기술이 포함됩니다.  [방법: AutoSize 속성과 TableLayoutPanel 컨트롤을 사용하여 Windows Forms 지역화 지원](http://msdn.microsoft.com/library/1zkt8b33\(v=vs.110\))을 참조하세요.  
  
## 각 문화권에 대해 하나의 단일 배포 생성  
 이 배포 전략에서는 여러 배포를 생성합니다.  각 배포에는 특정 문화권에 필요한 위성 어셈블리만 포함하고 배포를 해당 문화권과 관련된 것으로 표시합니다.  
  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서 이 메서드를 사용하려면 원하는 지역의 **게시** 탭에서 **언어 게시** 속성을 설정합니다.  [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서는 선택된 지역에 필요한 위성 어셈블리를 자동으로 포함하고 기타 모든 위성 어셈블리를 배포에서 제외합니다.  
  
 Microsoft [!INCLUDE[winsdklong](../deployment/includes/winsdklong_md.md)]에서 MageUI.exe 도구를 사용하여 같은 작업을 수행할 수 있습니다.  응용 프로그램 매니페스트의 **파일** 탭에서 **채우기** 단추를 사용하여 기타 모든 위성 어셈블리를 응용 프로그램 디렉터리에서 제외하고 MageUI.exe의 배포 매니페스트에 대한 **이름** 탭에서 **문화권** 필드를 설정합니다.  이러한 단계에서는 올바른 위성 어셈블리를 포함하고 배포 매니페스트의 `assemblyIdentity` 요소에서 `language` 특성을 해당 문화권으로 설정합니다.  
  
 응용 프로그램을 게시하고 나서 응용 프로그램이 지원하는 각 추가 문화권에 대해 이 단계를 반복해야 합니다.  매번 다른 웹 서버 디렉터리 또는 파일 공유 디렉터리에 게시하는지 확인해야 합니다. 이는 각 응용 프로그램 매니페스트는 다른 위성 어셈블리를 참조하고 각 배포 매니페스트에는 `language` 특성의 다른 값이 포함되기 때문입니다.  
  
## 요청 시 위성 어셈블리 다운로드  
 모든 위성 어셈블리를 단일 배포에 포함하도록 결정하면 어셈블리를 선택 사항으로 표시할 수 있는 요청 시 다운로드를 사용하여 성능을 향상할 수 있습니다.  응용 프로그램이 설치되거나 업데이트될 때는 표시된 어셈블리가 다운로드되지 않습니다.  필요할 때 <xref:System.Deployment.Application.ApplicationDeployment> 클래스에서 <xref:System.Deployment.Application.ApplicationDeployment.DownloadFileGroup%2A> 메서드를 호출하여 어셈블리를 설치할 수 있습니다.  
  
 요청 시 위성 어셈블리 다운로드는 요청 시 기타 유형 어셈블리를 다운로드하는 것과 약간 다릅니다.  [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]에 대해 [!INCLUDE[winsdkshort](../debugger/debug-interface-access/includes/winsdkshort_md.md)]도구를 사용하여 이 시나리오를 사용하도록 설정하는 방법에 대한 자세한 내용과 코드 예제는 [연습: ClickOnce 배포 API에서 요청 시 위성 어셈블리 다운로드](../deployment/walkthrough-downloading-satellite-assemblies-on-demand-with-the-clickonce-deployment-api.md)를 참조하세요.  
  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서 이 시나리오를 사용하도록 설정할 수도 있습니다.  또한 [연습: 디자이너를 사용하여 ClickOnce 배포 API에서 요청 시 위성 어셈블리 다운로드](http://msdn.microsoft.com/library/ms366788\(v=vs.110\)) 또는 [연습: 디자이너를 사용하여 ClickOnce 배포 API에서 요청 시 위성 어셈블리 다운로드](http://msdn.microsoft.com/library/ms366788\(v=vs.120\))를 참조하세요.  
  
## 배포하기 전에 지역화된 ClickOnce 응용 프로그램 테스트  
 위성 어셈블리는 응용 프로그램의 주 스레드에 대한 <xref:System.Threading.Thread.CurrentUICulture%2A> 속성이 위성 어셈블리의 문화권으로 설정된 경우에만 Windows Forms 응용 프로그램에 사용됩니다.  로컬 시장의 고객은 이미 문화권이 해당 기본값으로 설정된 지역화된 Windows 버전을 실행하고 있을 수 있습니다.  
  
 응용 프로그램을 고객에게 제공하기 전에 지역화된 배포를 테스트하는 세 가지 옵션이 있습니다.  
  
-   해당하는 지역화 버전 Windows에서 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램을 실행할 수 있습니다.  
  
-   응용 프로그램에서 <xref:System.Threading.Thread.CurrentUICulture%2A> 속성을 프로그래밍 방식으로 설정할 수 있습니다.  <xref:System.Windows.Forms.Application.Run%2A> 메서드를 호출하기 전에 이 속성을 설정해야 합니다.  
  
## 참고 항목  
 [\<assemblyIdentity\> 요소](../deployment/assemblyidentity-element-clickonce-deployment.md)   
 [ClickOnce 보안 및 배포](../deployment/clickonce-security-and-deployment.md)   
 [Windows Forms 전역화](../Topic/Globalizing%20Windows%20Forms.md)