---
title: "빠른 시작: Visual Studio의 템플릿에서 Python 프로젝트 만들기 | Microsoft Docs"
ms.custom: 
ms.date: 09/25/2017
ms.reviewer: 
ms.suite: 
ms.technology: devlang-python
ms.devlang: python
ms.tgt_pltfrm: 
ms.topic: article
caps.latest.revision: "1"
author: kraigb
ms.author: kraigb
manager: ghogen
ms.workload: python
ms.openlocfilehash: ee329df0bda8869215969941024deba6d94743fe
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="quickstart-create-a-python-project-from-a-template-in-visual-studio"></a>빠른 시작: Visual Studio의 템플릿에서 Python 프로젝트 만들기

[Visual Studio 2017에 Python 지원을 설치](installation.md)하면 다양한 템플릿을 사용하여 새 Python 프로젝트를 쉽게 만들 수 있습니다.

1. Visual Studio를 실행합니다.

1. **파일 > 새로 만들기 > 프로젝트**(Ctrl+Shift+N)를 선택합니다. **새 프로젝트** 대화 상자에서 "Python"을 검색하고, 원하는 템플릿을 선택합니다. 템플릿을 선택하면 템플릿이 제공하는 것의 간단한 설명이 표시됩니다. ([Python 프로젝트](python-projects.md#project-templates)도 참조)

    ![Python 템플릿이 있는 VS2017 새 프로젝트 대화 상자](media/projects-new-project-dialog2.png)

1. 이 빠른 시작의 경우 "Python 응용 프로그램" 템플릿을 선택하고, 프로젝트에 이름(예: "MakePI") 및 위치를 지정하고, **확인**을 선택합니다. 

1. Visual Studio는 템플릿에 설명된 대로 다른 파일과 함께 프로젝트 파일(디스크의 `.pyproj` 파일)을 만듭니다. "Python 응용 프로그램" 템플릿을 사용하여 프로젝트는 프로젝트와 같은 이름이 지정된 하나의 빈 파일만을 포함합니다. 파일은 기본적으로 Visual Studio 편집기에서 열립니다.

    ![Python 응용 프로그램 템플릿을 사용하는 경우 결과 프로젝트](media/projects-new-structure.png)

1. PI의 1000자리를 계산하고 표시하는 아래 코드와 같이 열린 파일에 일부 코드를 추가합니다.

    ```python
    """ Print digits of PI; code adapted from the second, shorter solution
    at http://www.codecodex.com/wiki/Calculate_digits_of_pi#Python
    """

    from time import perf_counter

    def pi_digits_Python(digits):
        scale = 10000
        maxarr = int((digits / 4) * 14)
        arrinit = 2000
        carry = 0
        arr = [arrinit] * (maxarr + 1)
        output = ""

        for i in range(maxarr, 1, -14):
            total = 0
            for j in range(i, 0, -1):
                total = (total * j) + (scale * arr[j])
                arr[j] = total % ((j * 2) - 1)
                total = total / ((j * 2) - 1)

            output += "%04d" % (carry + (total / scale))
            carry = total % scale

        return output;

    def test_py():
        digits = 1000;

        start = perf_counter()
        output = pi_digits_Python(digits);
        elapsed = perf_counter() - start;

        print("PI to " + str(digits) + " digits in " + str(int(elapsed * 10000)/10000) + " seconds:")

        ## replace inserts the decimal point
        print(output.replace("3", "3.", 1))

    if __name__ == "__main__":
        test_py();
    ```

1. Ctrl+F5 키를 누르거나 메뉴에서 **디버그 > 디버깅하지 않고 시작**을 선택하여 프로그램을 실행합니다. 결과는 콘솔 창에 표시됩니다.

## <a name="next-steps"></a>다음 단계

> [!div class="nextstepaction"]
> [자습서: Visual Studio에서 Python 작업](vs-tutorial-01-01.md)

## <a name="see-also"></a>참고 항목

- [기존 Python 인터프리터에 대한 환경 만들기](python-environments.md#creating-an-environment-for-an-existing-interpreter)
- [Visual Studio 2015 이하 버전에서 Python 지원 설치](installation.md)
- [설치 위치](installation.md#install-locations).
