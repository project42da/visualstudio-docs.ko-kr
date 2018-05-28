---
title: 내게 적합한 게시 옵션
ms.date: 03/09/2017
ms.reviewer: riande
ms.prod: visual-studio-dev15
ms.technology: vs-ide-deployment
ms.topic: conceptual
helpviewer_keywords:
- ASP.NET, web applications, deployment, publishing
ms.assetid: 3A13F685-531C-457D-A98E-631888011E4B
author: Mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0fd980aa7da59c98348c4dede5aee9835863d522
ms.sourcegitcommit: 209c2c068ff0975994ed892b62aa9b834a7f6077
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/17/2018
---
# 내게 적합한 게시 옵션

Visual Studio 내에서 웹 응용 프로그램을 다음 대상에 직접 게시할 수 있습니다.

- [Azure App Service](#azure-app-service)
- [Azure Virtual Machines](#azure-virtual-machines)
- [파일 시스템](#file-system)
- [사용자 지정 대상(IIS, FTP 등)](#custom-targets)(임의의 모든 웹 서버 포함)

**게시** 탭에서 기존 게시 프로필을 선택하거나, 기존 게시 프로필을 가져오거나, 여기에 설명된 옵션을 사용하여 새로 만들 수 있습니다. 다양한 앱 형식에 대한 IDE에서 게시 옵션을 둘러보려면 [배포 소개](../../deployment/deploying-applications-services-and-components.md)를 참조하세요.

## Azure App Service Web Apps

[Azure App Service Web Apps(또는 Web Apps)](/azure/app-service/app-service-web-overview)는 개발자가 인프라를 유지 관리하지 않고 확장 가능한 여러 웹 응용 프로그램과 서비스를 빠르게 만드는 데 도움이 됩니다.

포함하는 App Service에 대한 [가격 책정 계층 또는 계획](/azure/app-service/azure-web-sites-web-hosting-plans-in-depth-overview)을 선택하여 웹앱의 컴퓨팅 성능을 확인합니다. 가격 책정 계층을 변경하지 않고 여러 Web Apps(및 기타 앱 유형)에서 동일한 App Service를 공유하도록 할 수도 있습니다. 예를 들어 개발, 스테이징 및 프로덕션 Web Apps를 동일한 App Service에서 함께 호스트할 수 있습니다.

App Service는 Azure의 클라우드 호스트 가상 컴퓨터에서 실행되지만 이러한 가상 컴퓨터가 자동으로 관리됩니다. App Service의 각 웹앱에는 고유한 \*.azurewebsites.net URL이 할당됩니다. 무료 이외의 모든 가격 책정 계층에서는 사용자 지정 도메인 이름을 사이트에 할당할 수 있습니다.

### Azure App Service Web Apps를 선택해야 하는 경우

- 인터넷을 통해 액세스할 수 있는 웹 응용 프로그램을 배포하려고 합니다.
- 다시 배포할 필요가 없도록 수요에 따라 웹 응용 프로그램을 자동으로 크기를 조정하려고 합니다.
- 서버 인프라(소프트웨어 업데이트 포함)를 유지 관리하지 않으려고 합니다.
- 웹 응용 프로그램을 호스트하는 서버에서 컴퓨터 수준 사용자 지정을 하지 않아도 됩니다.

> 사용자 고유의 데이터 센터 또는 다른 온-프레미스 컴퓨터에서 Azure App Service를 사용하려는 경우 [Azure Stack](https://azure.microsoft.com/overview/azure-stack/)을 사용하면 됩니다.

ASP.NET Core 앱 게시에 대한 자세한 내용은 [Visual Studio를 사용하여 Azure App Service에 ASP.NET Core 웹앱 게시](/aspnet/core/tutorials/publish-to-azure-webapp-using-vs)를 참조하세요.

## Azure Virtual Machines

[Azure VM(Virtual Machines)](https://azure.microsoft.com/documentation/services/virtual-machines/)을 사용하면 개수에 관계없이 클라우드에서 컴퓨팅 리소스를 만들고 관리할 수 있습니다. VM의 모든 소프트웨어 및 업데이트에 대한 책임을 지고 웹 응용 프로그램에 필요한 경우 원하는 대로 사용자 지정할 수 있습니다. 원격 데스크톱을 통해 가상 컴퓨터에 직접 액세스할 수 있으며, 각 가상 컴퓨터에서 필요한 기간 동안 할당된 IP 주소를 유지 관리합니다.

가상 컴퓨터에 호스트된 웹 응용 프로그램의 크기를 조정하려면 수요에 따라 추가 VM을 구동한 다음 필요한 소프트웨어를 배포해야 합니다. 이러한 추가 수준의 제어를 통해 지역마다 다르게 크기를 조정할 수 있습니다. 예를 들어 응용 프로그램이 다양한 지역 사무소의 직원에게 서비스를 제공하는 경우 해당 지역의 직원 수에 따라 VM의 크기를 조정하여 비용을 절감할 수 있습니다.

자세한 내용은 Azure App Service, Azure Virtual Machines 및 Visual Studio의 사용자 지정 옵션을 통해 배포 대상으로 사용할 수 있는 다른 Azure 서비스 간의 [상세 비교](https://azure.microsoft.com/documentation/articles/choose-web-site-cloud-service-vm/)를 참조하세요.

### Azure App Virtual Machines를 선택해야 하는 경우

- 인터넷을 통해 액세스할 수 있고, 할당된 IP 주소의 수명 주기 동안 모든 권한을 가진 웹 응용 프로그램을 배포하려고 합니다.
- 특수 데이터베이스 시스템, 특정 네트워킹 구성, 디스크 파티션 등의 추가 소프트웨어를 포함하는 컴퓨터 수준 사용자 지정이 서버에 필요합니다.
- 웹 응용 프로그램의 크기 조정을 세부적으로 제어하려고 합니다.
- 기타 다른 이유로 응용 프로그램을 호스트하는 서버에 대한 직접적인 액세스가 필요합니다.

> 사용자 고유의 데이터 센터 또는 다른 온-프레미스 컴퓨터에서 Azure Virtual Machines를 사용하려는 경우 [Azure Stack](https://azure.microsoft.com/overview/azure-stack/)을 사용하면 됩니다.


## 파일 시스템

파일 시스템에 배포하는 경우 사용자 컴퓨터의 특정 폴더에 웹 응용 프로그램의 파일을 복사하면 됩니다. 이 작업은 주로 테스트를 위해 또는 컴퓨터에서 웹 서버도 실행하는 경우 제한된 수의 사용자가 사용할 응용 프로그램을 배포하기 위해 사용됩니다. 대상 폴더가 네트워크에서 공유되는 경우 파일 시스템에 배포하면 웹 응용 프로그램 파일을 특정 서버에 배포할 수 있는 다른 사용자들이 사용할 수 있게 됩니다.

구성된 방식이나 연결된 네트워크에 따라 웹 서버를 실행하는 모든 로컬 컴퓨터가 인터넷 또는 인트라넷을 통해 응용 프로그램을 제공할 수 있습니다. 컴퓨터를 인터넷에 직접 연결하는 경우 외부 보안 위협으로부터 보호하기 위해 특히 주의해야 합니다. 이러한 컴퓨터를 직접 관리하기 때문에 소프트웨어 및 하드웨어 구성에 대한 모든 권한을 갖습니다.

어떤 이유(예: 컴퓨터 액세스)로든 Azure App Service 또는 Azure Virtual Machines와 같은 클라우드 서비스를 사용할 수 없는 경우 고유한 데이터 센터의 [Azure Stack](https://azure.microsoft.com/overview/azure-stack/)을 사용할 수 있습니다. Azure Stack을 사용하면 모든 항목을 온-프레미스에서 유지하면서 Azure App Service 및 Azure Virtual Machines를 통해 컴퓨팅 리소스를 관리하고 사용할 수 있습니다.

### 파일 시스템 배포를 선택해야 하는 경우

- 파일 공유에만 응용 프로그램을 배포하면 되며, 다른 사용자는 여기서 다른 서버에 배포합니다.
- 로컬 테스트 배포만 있으면 됩니다.
- 다른 배포 대상에 보내기 전에 응용 프로그램 파일을 개별적으로 검사하고 수정하려고 합니다.

.NET Core 앱 배포에 대한 자세한 내용은 [Visual Studio를 사용하여 .NET Core 앱 배포](/dotnet/core/deploying/deploy-with-vs)를 참조하세요.

## 사용자 지정 대상

사용자 지정 대상을 사용하면 Azure App Service, Azure Virtual Machines 또는 로컬 파일 시스템 이외의 대상에 웹 응용 프로그램을 배포할 수 있습니다. 파일 시스템 또는 다른 클라우드 서비스의 서버를 포함하여 액세스 권한이 있는 다른 서버(인터넷 또는 인트라넷)에 배포할 수 있습니다. 웹 배포(파일 또는 .ZIP) 및 FTP에서 작동합니다.

사용자 지정 대상을 선택하는 경우 Visual Studio에서 프로필 이름을 묻는 메시지를 표시한 다음 대상 서버 또는 위치, 사이트 이름, 자격 증명 등의 **연결** 정보를 추가로 수집합니다. **설정** 탭에서 다음 동작을 제어할 수 있습니다.

- 배포하려는 구성
- 대상에서 기존 파일을 제거할지 여부
- 게시 중에 미리 컴파일할지 여부
- 배포에서 App_Data 폴더의 파일을 제외할지 여부

Visual Studio에서 원하는 수의 사용자 지정 배포 프로필을 만들 수 있으므로 다른 설정으로 프로필을 관리할 수 있습니다.

### 사용자 지정 배포를 선택해야 하는 경우

- URL을 통해 액세스할 수 있는 Azure 이외의 공급자에서 클라우드 서비스를 사용하고 있습니다.
- Visual Studio 내에서 사용하거나 Azure 계정에 직접 연결된 것 이외의 자격 증명을 사용하여 배포하려고 합니다.
- 배포할 때마다 대상에서 파일을 삭제하려고 합니다.

IIS에 게시하는 방법에 대한 자세한 내용은 [ASP.NET 3.5 및 ASP.NET 4.5를 사용하는 IIS 8.0](/iis/get-started/whats-new-in-iis-8/iis-80-using-aspnet-35-and-aspnet-45) 및 [원격 IIS 컴퓨터에서 ASP.NET 원격 디버그](../../debugger/remote-debugging-aspnet-on-a-remote-iis-7-5-computer.md)를 참조하세요.
