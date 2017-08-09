---
title: "Python용 Azure SDK | Microsoft Docs"
ms.custom: 
ms.date: 3/7/2017
ms.prod: visual-studio-dev15
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-python
ms.devlang: python
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d30fddae-8e2f-4f50-90d3-8ed2cd35c7a6
caps.latest.revision: 11
author: kraigb
ms.author: kraigb
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: c00adbbabf0d3b82acb17f4a269dfc693246bc69
ms.openlocfilehash: 89de0d11791dbf13b9d4fcfcea8168b443d2777b
ms.contentlocale: ko-kr
ms.lasthandoff: 08/01/2017

---

# <a name="azure-sdk-for-python"></a>Python용 Azure SDK

Python용 Azure SDK를 사용하면 Windows, Mac OSX 및 Linux에서 실행되는 응용 프로그램에서 Microsoft Azure 서비스를 쉽게 사용하고 관리할 수 있습니다.

## <a name="installation"></a>설치

Azure SDK는 [Python 패키지 인덱스](https://pypi.python.org/pypi/azure)에서 설치됩니다.

다음과 같이 **안정적인 최신 버전**(Python 2.7 및 3.3+ 지원)을 설치합니다.

```bash
pip install azure
```

또한 Azure 설명서에서 [Python 및 SDK 설치](https://azure.microsoft.com/documentation/articles/python-how-to-install/)를 수행할 수도 있습니다.

## <a name="documentation"></a>설명서

설명서는 [azure-sdk-for-python.readthedocs.org](http://azure-sdk-for-python.readthedocs.org/en/latest/index.html)에 있습니다.

[Python용 Azure SDK 개발자 센터](http://azure.microsoft.com/develop/python/)에는 다음과 같은 여러 가지 자습서를 포함하여 유용한 리소스도 많이 있습니다.

  - [Django](https://docs.microsoft.com/azure/app-service-web/web-sites-python-create-deploy-django-app) [Flask](https://docs.microsoft.com/azure/app-service-web/web-sites-python-create-deploy-flask-app) 및 [Bottle](https://docs.microsoft.com/azure/app-service-web/web-sites-python-create-deploy-bottle-app)을 사용하여 웹앱 만들기
  - [Blob 저장소](https://docs.microsoft.com/azure/storage/storage-python-how-to-use-blob-storage)
  - [테이블 저장소](https://docs.microsoft.com/azure/storage/storage-python-how-to-use-table-storage)
  - [큐 저장소](https://docs.microsoft.com/azure/storage/storage-python-how-to-use-queue-storage)
  - [DocumentDB](https://docs.microsoft.com/azure/documentdb/documentdb-python-application)
  - [Service Bus 큐](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-python-how-to-use-queues)
  - [Service Bus 토픽/구독](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-python-how-to-use-topics-subscriptions)
  - [Python에서 서비스 관리를 사용하는 방법](https://docs.microsoft.com/azure/cloud-services/cloud-services-python-how-to-use-service-management)

설명서가 없는 공용 API의 경우 [SDK의 GitHub 리포지토리](https://github.com/Azure/azure-sdk-for-python)에 있는 단위 테스트가 좋은 정보 자료가 됩니다.

- [저장소 단위 테스트](https://github.com/Azure/azure-storage-python/tree/master/tests)
- [Service Bus 단위 테스트](https://github.com/Azure/azure-sdk-for-python/tree/master/azure-servicebus/tests)
- [서비스 관리 단위 테스트](https://github.com/Azure/azure-sdk-for-python/tree/master/azure-servicemanagement-legacy/tests)
- [리소스 관리 단위 테스트](https://github.com/Azure/azure-sdk-for-python/tree/master/azure-mgmt/tests)

## <a name="support"></a>Support(지원)

SDK용 Git 리포지토리는 [https://github.com/Azure/azure-sdk-for-python](https://github.com/Azure/azure-sdk-for-python)에 있습니다.

문제를 발견하거나 SDK 사용에 대한 질문이 있는 경우 [리포지토리에 문제를 보고](https://github.com/Azure/azure-sdk-for-python/issues)해 주세요.

