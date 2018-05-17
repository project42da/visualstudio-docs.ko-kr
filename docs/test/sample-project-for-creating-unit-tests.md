---
title: 단위 테스트를 만들기 위한 예제 코드
description: 이 문서에서는 Visual Studio에서 단위 테스트로 테스트할 수 있는 샘플 코드를 제공합니다.
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: sample
helpviewer_keywords:
- unit test sample [Visual Studio]
- unit tests, samples
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 93a6627b96daefa48c9a72fd84726775fc449bde
ms.sourcegitcommit: fe5a72bc4c291500f0bf4d6e0778107eb8c905f5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="sample-code-for-testing"></a>테스트를 위한 샘플 코드

이 샘플 코드에는 단위 테스트를 통해 테스트할 수 있는 *BankAccount* 클래스가 포함되어 있습니다.

이 코드는 다음 연습에서 사용됩니다.

- [관리 코드에 대한 단위 테스트 만들기 및 실행](../test/walkthrough-creating-and-running-unit-tests-for-managed-code.md). 이 연습에서는 단위 테스트를 작성, 사용자 지정 및 실행하고 테스트 결과를 검사하는 단계를 안내합니다.
- [명령줄 테스트 유틸리티 사용](http://msdn.microsoft.com/Library/52c11992-9e94-4067-a4b7-59f19d69d867). 이 연습에서는 MSTest.exe 명령줄 유틸리티를 사용하여 테스트를 실행하고 결과를 확인합니다.

## <a name="sample-code"></a>샘플 코드

이 샘플에서 의도적으로 발생시켜야 하는 오류는 Debit 메서드 "m_balance += amount"의 등호 앞에 더하기 기호가 아닌 빼기 기호가 있어야 한다는 것뿐입니다.

```csharp
using System;

namespace BankAccountNS
{
    /// <summary>
    /// Bank Account demo class.
    /// </summary>
    public class BankAccount
    {
        private string m_customerName;

        private double m_balance;

        private bool m_frozen = false;

        private BankAccount()
        {
        }

        public BankAccount(string customerName, double balance)
        {
            m_customerName = customerName;
            m_balance = balance;
        }

        public string CustomerName
        {
            get { return m_customerName; }
        }

        public double Balance
        {
            get { return m_balance; }
        }

        public void Debit(double amount)
        {
            if (m_frozen)
            {
                throw new Exception("Account frozen");
            }

            if (amount > m_balance)
            {
                throw new ArgumentOutOfRangeException("amount");
            }

            if (amount < 0)
            {
                throw new ArgumentOutOfRangeException("amount");
            }

            m_balance += amount; // intentionally incorrect code
        }

        public void Credit(double amount)
        {
            if (m_frozen)
            {
                throw new Exception("Account frozen");
            }

            if (amount < 0)
            {
                throw new ArgumentOutOfRangeException("amount");
            }

            m_balance += amount;
        }

        private void FreezeAccount()
        {
            m_frozen = true;
        }

        private void UnfreezeAccount()
        {
            m_frozen = false;
        }

        public static void Main()
        {
            BankAccount ba = new BankAccount("Mr. Bryan Walton", 11.99);

            ba.Credit(5.77);
            ba.Debit(11.22);
            Console.WriteLine("Current balance is ${0}", ba.Balance);
        }
    }
}
```

/* 이 문서에 사용된 예제 회사, 조직, 제품, 도메인 이름, 전자 메일 주소, 로고, 사람, 장소 및 이벤트는 실제 데이터가 아닙니다. 어떠한 실제 회사, 기관, 제품, 도메인 이름, 전자 메일 주소, 로고, 사람, 장소 또는 이벤트와도 연관시킬 의도가 없으며 그렇게 유추해서도 안 됩니다. \*/

## <a name="create-the-project"></a>프로젝트를 만듭니다.

이 코드로 작업하려면 먼저 Visual Studio에서 이를 위한 프로젝트를 만듭니다. [연습: 관리 코드에 대한 단위 테스트 만들기 및 실행](../test/walkthrough-creating-and-running-unit-tests-for-managed-code.md#create-a-project-to-test)에서 프로젝트를 만드는 단계를 수행합니다.

## <a name="see-also"></a>참고 항목

- [연습: 관리 코드에 대한 단위 테스트 만들기 및 실행](../test/walkthrough-creating-and-running-unit-tests-for-managed-code.md)
- [연습: 명령줄 테스트 유틸리티 사용](http://msdn.microsoft.com/Library/52c11992-9e94-4067-a4b7-59f19d69d867)
