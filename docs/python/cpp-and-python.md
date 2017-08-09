---
title: "Visual Studio에서 C++ 및 Python 사용 | Microsoft 문서"
ms.custom: 
ms.date: 7/12/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-python
ms.devlang: python
ms.tgt_pltfrm: 
ms.topic: get-started-article
ms.assetid: f7dbda92-21bf-4af0-bb34-29b8bf231f32
description: "Visual Studio에서 Python용 C++ 확장 또는 모듈을 작성하는 프로세스 amd 단계"
caps.latest.revision: 1
author: kraigb
ms.author: kraigb
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6d25db4639f2c8391c1e32542701ea359f560178
ms.openlocfilehash: 6128d78b99b7fa82ffd5676678a49b1b6a0de177
ms.contentlocale: ko-kr
ms.lasthandoff: 07/18/2017

---

# <a name="creating-a-c-extension-for-python"></a>Python용 C++ 확장 만들기

C++(또는 C)로 작성된 모듈은 하위 수준 운영 체제 기능에 대한 액세스를 가능하게 할 뿐만 아니라 Python 인터프리터의 기능을 확장하는 데 일반적으로 사용됩니다. 모듈은 세 가지 기본 형식이 있습니다.

- 액셀러레이터 모듈: Python은 해석된 언어이기 때문에 성능 향상을 위해 특정 코드 부분을 C++로 작성할 수 있습니다. 
- 래퍼 모듈: 래퍼는 기존 C/C++ 인터페이스를 Python 코드에 노출하거나 Python에서 사용하기 쉬운 보다 “Python” 최적화된 API를 노출합니다.
- 하위 수준 시스템 액세스 모듈: CPython 런타임, 운영 체제 또는 기본 하드웨어의 하위 수준 기능에 액세스하기 위해 만들었습니다. 

이 항목에서는 쌍곡 탄젠트를 계산하고 Python 코드에서 호출하는 CPython용 C++ 확장을 빌드하는 방법에 대해 설명합니다. C++에서 동일한 루틴을 구현할 경우의 성능 향상을 보여 주기 위해 Python에서 먼저 루틴을 구현합니다.

여기에서 사용된 방법은 [Python 설명서](https://docs.python.org/3/c-api/)에 설명된 대로 표준 CPython 확장용입니다. 이 방법과 다른 방법의 비교는 이 항목의 끝에 있는 [대체 방법](#alternative-approaches)에 설명되어 있습니다.

## <a name="prerequisites"></a>필수 구성 요소

이 연습은 기본 옵션(예: Python 3.6을 기본 인터프리터로 사용)으로 **C++를 사용한 데스크톱 개발** 및 **Python 개발** 워크로드를 사용하는 Visual Studio 2017용으로 작성되었습니다. **Python 개발** 워크로드에서는 **Python 네이티브 개발 도구**의 오른쪽에 있는 확인란을 선택합니다. 그러면 이 항목에 설명된 대부분의 옵션이 설정됩니다. 이 옵션에는 C++ 워크로드도 자동으로 포함됩니다. 

![Python 네이티브 개발 도구 옵션 선택](media/cpp-install-native.png)

다른 버전의 Visual Studio 사용을 포함한 자세한 내용은 [Visual Studio용 Python 지원 설치](installation.md)를 참조하세요. Python을 별도로 설치하는 경우 설치 관리자의 **고급 옵션**에서 **디버깅 기호 다운로드** 및 **디버그 버전의 이진 파일 다운로드**를 선택해야 합니다. 이 옵션은 디버그 빌드를 수행하도록 선택할 경우 필요한 디버그 라이브러리를 사용할 수 있도록 합니다.

> [!Note]
> Python은 Anaconda 3 64비트(CPython 최신 버전 포함) 및 **Python 네이티브 개발 도구** 옵션을 기본적으로 포함하는 **데이터 과학 및 분석 응용 프로그램** 워크로드를 통해서도 사용할 수 있습니다.

## <a name="create-the-python-application"></a>Python 응용 프로그램 만들기

1. **파일 > 새로 만들기 > 프로젝트**를 선택하여 Visual Studio에서 새 Python 프로젝트를 만듭니다. “Python”을 검색하고 **Python 응용 프로그램** 템플릿을 선택한 다음 적합한 이름과 위치를 지정하고 **확인**을 선택합니다.

1. 프로젝트의 `.py` 파일에서 쌍곡 탄젠트 계산(더 쉬운 비교를 위해 수학 라이브러리를 사용하지 않고 구현됨)을 벤치마크하는 다음 코드를 붙여넣습니다. 언제든지 코드를 수동으로 입력하여 [Python 편집 기능](code-editing.md)의 일부를 경험해 보세요.

    ```python
    from itertools import islice
    from random import random
    from time import perf_counter

    COUNT = 100000
    DATA = list(islice(iter(lambda: (random() - 0.5) * 3.0, None), COUNT))

    e = 2.7182818284590452353602874713527

    def sinh(x):
        return (1 - (e ** (-2 * x))) / (2 * (e ** -x))

    def cosh(x):
        return (1 + (e ** (-2 * x))) / (2 * (e ** -x))

    def tanh(x):
        tanh_x = sinh(x) / cosh(x)
        return tanh_x

    def sequence_tanh(data):
        '''Applies the hyperbolic tanger function to map all values in
        the sequence to a value between -1.0 and 1.0.
        '''
        result = []
        for x in data:
            result.append(tanh(x))
        return result

    def test(fn, name):
        start = perf_counter()

        result = fn(DATA)

        duration = perf_counter() - start
        print('{} took {:.3f} seconds\n\n'.format(name, duration))

        for d in result:
            assert -1 <= d <=1, " incorrect values"

    if __name__ == "__main__":
        test(sequence_tanh, 'sequence_tanh')

        test(lambda d: [tanh(x) for x in d], '[tanh(x) for x in d]')
    ```

1. **디버그 > 디버깅하지 않고 시작**(Ctrl+F5)을 사용하여 프로그램을 실행하고 결과를 확인합니다. 각 벤치마크를 완료하려면 몇 초 정도 걸립니다.

## <a name="create-the-core-c-project"></a>핵심 C++ 프로젝트 만들기

1. 솔루션 탐색기에서 솔루션을 마우스 오른쪽 단추로 클릭하고 **추가 > 새 프로젝트...**를 선택합니다. Visual Studio 솔루션에는 Python 및 C++ 프로젝트가 함께 포함될 수 있습니다.

1. “C++”를 검색하고, **빈 프로젝트**를 선택하고, 이름(예: TanhBenchmark)을 지정한 다음 **확인**을 선택합니다. 참고: Visual Studio 2017과 함께 **Python 네이티브 개발 도구**를 설치한 경우 여기에 설명된 내용이 이미 많이 포함되어 있는 **Python 확장 모듈** 템플릿으로 시작할 수 있습니다. 그러나 이 연습에서는 빈 프로젝트로 시작하여 확장 모듈 빌드를 단계별로 보여 줍니다.

1. 새 프로젝트에서 **소스 파일** 노드를 마우스 오른쪽 단추로 클릭하여 C++ 파일을 만들고, **추가 > 새 항목..."**을 선택하고 **C++ 파일**을 선택하여 이름(예: `module.cpp`)을 지정한 다음 **확인**을 선택합니다. 이 단계는 다음 단계에서 C++ 속성 페이지를 설정하는 데 필요합니다.

1. 새 프로젝트를 마우스 오른쪽 단추로 클릭하고 **속성**을 선택한 다음 표시되는 **속성 페이지** 대화 상자 맨 위에서 **구성**을 **모든 구성**으로 설정합니다.

1. 아래에 설명된 대로 특정 속성을 설정한 다음 **적용**을 선택합니다. **적용** 단추를 활성화하려면 편집 가능한 필드 외부를 클릭해야 할 수 있습니다.

    | 탭 | 속성 | 값 | 
    | --- | --- | --- |
    | 일반 | 일반 > 대상 이름 | Python에 표시되는 모듈의 이름과 정확하게 일치하도록 이 필드를 설정합니다. |
    | | 일반 > 대상 확장명 | .pyd |
    | | 프로젝트 기본값 > 구성 형식 | 동적 라이브러리(.dll) |
    | C/C++ > 일반 | 추가 포함 디렉터리 | 설치에 맞게 Python `include` 폴더를 추가합니다(예: `c:\Python36\include`). |     
    | C/C++ > 코드 생성 | 런타임 라이브러리 | 다중 스레드 DLL(/ MD)(아래 경고 참조) |
    | C/C++ > 전처리기 | 전처리기 정의 | 문자열의 시작 부분에 `Py_LIMITED_API;`를 추가합니다. 그러면 Python에서 호출할 수 있는 일부 함수가 제한되고 다른 버전의 Python 간 코드 이식성이 향상됩니다. |
    | 링커 > 일반 | 추가 라이브러리 디렉터리 | `.lib` 파일을 포함하는 Python `lib` 폴더를 설치에 맞게 추가합니다(예: `c:\Python36\libs`). `.py` 파일을 포함하는 `Lib` 폴더가 *아니라* `.lib` 파일을 포함하는 `libs` 폴더를 가리켜야 합니다. | 

    > [!Tip]
    > C/C++ 탭이 표시되지 않는 경우 프로젝트에 C/C++ 소스 파일로 식별되는 파일이 포함되어 있지 않기 때문입니다. `.c` 또는 `.cpp` 확장명을 사용하지 않고 소스 파일을 만드는 경우 이런 상태가 발생할 수 있습니다. 예를 들어 이전의 새 항목 대화 상자에서 실수로 `module.cpp` 대신 `module.coo`를 입력한 경우 Visual Studio에서 파일을 만들지만, C/C++ 속성 탭을 활성화하는 “C/C++ 코드”로 파일 형식을 설정하지 않습니다. 파일 이름을 `.cpp`로 변경하는 경우에도 여전히 잘못 식별됩니다. 파일 형식을 제대로 설정하려면 솔루션 탐색기에서 파일을 마우스 오른쪽 단추로 클릭하고 **속성**을 선택한 다음 **파일 형식**을 **C/C++ 코드**로 설정합니다.

    > [!Warning]
    > 디버그 구성의 경우에도 **C/C++ > 코드 생성 > 런타임 라이브러리** 옵션을 “다중 스레드 디버그 DLL(/MDd)”로 설정하지 마세요. 디버그가 아닌 Python 이진 파일 작성에 사용되기 때문에 “다중 스레드 DLL(/MD)” 런타임을 선택합니다. /MDd 옵션을 설정한 경우 DLL의 디버그 구성을 빌드하면 *C1189: Py_LIMITED_API is incompatible with Py_DEBUG, Py_TRACE_REFS, and Py_REF_DEBUG*(C1189: Py_LIMITED_API가 Py_DEBUG, Py_TRACE_REFS 및 Py_REF_DEBUG와 호환되지 않음) 오류가 표시됩니다. 또한 빌드 오류를 방지하기 위해 `Py_LIMITED_API`를 제거하는 경우 모듈을 가져오려고 하면 Python이 충돌합니다. 뒷부분에 설명된 대로 충돌은 DLL의 `PyModule_Create` 호출 내에서 발생하고 *Fatal Python error: PyThreadState_Get: no current thread*(Python 오류: PyThreadState_Get: 현재 스레드 없음)라는 메시지가 출력됩니다.
    >
    > /MDd 옵션은 Python 디버그 이진 파일(예: python_d.exe)을 빌드하는 데 사용되지만 확장 DLL용으로 선택하면 `Py_LIMITED_API`에서 빌드 오류가 발생합니다.
   
1. C++ 프로젝트를 마우스 오른쪽 단추로 클릭하고 **빌드**를 선택하여 구성(디버그 및 릴리스)을 테스트합니다. `.pyd` 파일은 C++ 프로젝트 폴더 자체가 아니라 **디버그** 및 **릴리스** 아래의 *솔루션* 폴더에 있습니다.

1. C++ 프로젝트의 주 `.cpp` 파일에 다음 코드를 추가합니다.

    ```cpp
    #include <Windows.h>
    #include <cmath>    

    const double e = 2.7182818284590452353602874713527;

    double sinh_impl(double x) {
        return (1 - pow(e, (-2 * x))) / (2 * pow(e, -x));
    }

    double cosh_impl(double x) {
        return (1 + pow(e, (-2 * x))) / (2 * pow(e, -x));
    }

    double tanh(x) {
        return sinh(x) / cosh(x);
    }
    ```

1. C++ 프로젝트를 다시 빌드하여 코드가 올바른지 확인합니다.


## <a name="convert-the-c-project-to-an-extension-for-python"></a>C++ 프로젝트를 Python용 확장으로 변환

C++ DLL을 Python용 확장으로 만들려면 내보낸 메서드를 Python 형식과 상호 작용하도록 수정해야 합니다. 그런 다음 모듈의 메서드 정의와 함께 모듈을 내보내는 함수를 추가해야 합니다. 여기에 설명된 내용에 대한 배경 정보는 python.org에서 [Python/C API Reference Manual](https://docs.python.org/3/c-api/index.html)(Python/C API 참조 설명서) 및 특히 [Module Objects](https://docs.python.org/3/c-api/module.html)(모듈 개체)를 참조하세요. 오른쪽 위 드롭다운 컨트롤에서 Python의 버전을 선택해야 합니다.

1. C++ 파일의 맨 위에 `Python.h`를 포함합니다.

    ```cpp
    include <Python.h>
    ```

1. Python 형식을 허용하고 반환하도록 `tanh` 메서드를 수정합니다.

    ```cpp
    PyObject* tanh(PyObject *, PyObject* o) {
        double x = PyFloat_AsDouble(o);
        double tanh_x = sinh_impl(x) / cosh_impl(x);
        return PyFloat_FromDouble(tanh_x);
    }
    ```

1. C++ `tanh` 함수가 Python에 표시되는 방식을 정의하는 구조체를 추가합니다.

    ```cpp
    static PyMethodDef superfastcode_methods[] = {
        // The first property is the name exposed to python, the second is the C++ function name        
        { "fast_tanh", (PyCFunction)tanh, METH_O, nullptr },

        // Terminate the array with an object containing nulls.
        { nullptr, nullptr, 0, nullptr }
    };
    ```

1. Python에 표시되는 대로 모듈을 정의하는 구조체를 추가합니다.

    ```cpp
    static PyModuleDef superfastcode_module = {
        PyModuleDef_HEAD_INIT,
        "superfastcode",                        // Module name
        "Provides some functions, but faster",  // Module description
        0,
        superfastcode_methods                   // Structure that defines the methods
    };
    ```

1. Python에서 이름이 `PyInit_<module-name>`인 모듈을 로드할 때 호출하는 메서드를 추가합니다. 여기서 *&lt;module_name&gt;*은 C++ 프로젝트의 **일반 > 대상 이름** 속성과 정확하게 일치합니다. 즉, 프로젝트에서 빌드된 `.pyd`의 파일 이름과 일치합니다.

    ```cpp
    PyMODINIT_FUNC PyInit_superfastcode() {    
        return PyModule_Create(&superfastcode_module);
    }
    ```

1. DLL을 다시 빌드하여 코드를 확인합니다.

## <a name="test-the-code-and-compare-the-results"></a>코드를 테스트하고 결과 비교

DLL을 Python 확장으로 구조화했으므로 Python 프로젝트에서 참조하고, 모듈을 가져오며 해당 메서드를 사용할 수 있습니다.

Python에서 DLL을 사용할 수 있도록 설정하는 방법은 두 가지가 있습니다. 첫째, 두 프로젝트가 동일한 Visual Studio 솔루션에 있는 경우 Python 프로젝트에서 참조를 C++ 프로젝트에 추가할 수 있습니다.

1. 솔루션 탐색기에서 Python 프로젝트를 마우스 오른쪽 단추로 클릭하고 **참조**를 선택합니다. 대화 상자에서 **프로젝트** 탭을 선택하고 **superfastcode** 프로젝트, **확인**을 차례로 선택합니다.

둘째, 모듈을 글로벌 Python 환경에 설치하여 다른 Python 프로젝트에서도 사용 가능하도록 할 수 있습니다. 이 경우 일반적으로 해당 환경에 대한 IntelliSense 완성 데이터베이스를 새로 고쳐야 합니다. 환경에서 모듈을 제거하는 경우에도 새로 고침이 필요합니다.

1. Visual Studio 2017을 사용하고 있는 경우 Visual Studio 설치 관리자를 실행하고 **수정**을 선택한 다음 **개별 구성 요소 > 컴파일러, 빌드 도구 및 런타임 > Visual C++ 2015.3 v140 toolset**(Visual C++ 2015.3 v140 도구 집합)를 선택합니다. 이 단계가 필요한 이유는 Python(Windows용) 자체는 Visual Studio 2015(버전 14.0)로 빌드되며 여기에 설명된 메서드를 통해 확장을 빌드할 경우 이러한 도구를 사용할 수 있다고 예상하기 때문입니다.

1. C++ 프로젝트에서 **추가 > 새 항목...*을 선택하고 “Python”을 검색한 다음 **Python 파일**을 선택하여 이름을 setup.py로 지정하고 **확인**을 선택하여 `setup.py`라는 파일을 만듭니다. 편집기에 파일이 표시되면 다음 코드를 붙여넣습니다.

    ```python
    from distutils.core import setup, Extension, DEBUG

    sfc_module = Extension('superfastcode', sources = ['module.cpp'])

    setup(name = 'superfastcode', version = '1.0',
        description = 'Python Package with superfastcode C++ Extension',
        ext_modules = [sfc_module]
        )
    ```

    이 스크립트에 대한 설명서는 [Building C and C++ Extensions](https://docs.python.org/3/extending/building.html)(C 및 C++ 확장 빌드)(python.org)를 참조하세요.

1. `setup.py` 코드는 Visual Studio 2015 C++ 도구 집합을 사용하여 확장을 빌드하도록 Python에 지시하며, 명령줄에서 수행됩니다. 관리자 권한 명령 프롬프트를 열고 C++ 프로젝트 및 `setup.py`를 포함하는 폴더로 이동한 후 다음 명령을 입력합니다.

    ```bash
    pip install .
    ```

이제 `tanh` 코드를 모듈로 호출하고 Python 구현과 성능을 비교할 수 있습니다.

1. `tanhbenchmark.py`에서 다음 줄을 추가하여 DLL에서 가져온 `fast_tanh` 메서드를 호출하고 벤치마크 출력에 추가합니다. `from s` 문을 수동으로 입력하는 경우 `superfastcode`가 완성 목록에 표시되며, `import`를 입력하고 나면 `fast_tanh` 메서드가 나타납니다.

    ```python
    from superfastcode import fast_tanh    
    test(lambda d: [fast_tanh(x) for x in d], '[fast_tanh(x) for x in d]')
    ```

1. Python 프로그램을 실행합니다. C++ 루틴이 Python 구현보다 약 15~20배 더 빠르게 실행되는 것을 확인할 수 있습니다.

## <a name="debug-the-c-code"></a>C++ 코드 디버그

[Visual Studio의 Python 지원](installation.md)에는 [Python 및 C++ 코드를 함께 디버그](debugging-mixed-mode.md)하는 기능이 포함됩니다. 이 혼합 모드 디버깅을 사용해보려면 다음 단계를 수행합니다.

1. 솔루션 탐색기에서 Python 프로젝트를 마우스 오른쪽 단추로 클릭하고 **속성**, **디버그** 탭을 차례로 선택한 다음 **디버그 > 네이티브 코드 디버깅 사용** 옵션을 선택합니다.

    > [!Tip]
    > 네이티브 코드 디버깅을 사용하면 프로그램이 완료되었을 때 일반적인 “계속하려면 아무 키나 누르세요.” 일시 중지를 제공하지 않고 Python 출력 창이 바로 사라질 수 있습니다. 강제로 일시 중지하려면 네이티브 코드 디버깅을 사용할 때 **디버그** 탭의 **실행 > 인터프리터 인수** 필드에 `-i` 옵션을 추가합니다. 이 인수는 코드가 완료된 후 Python 인터프리터를 대화형 모드로 전환하며, 이때 Ctrl+Z, Enter 키를 눌러 종료할 때까지 대기합니다. 또는 Python 코드를 수정하지 않으려면 프로그램의 끝에 `import os` 및 `os.system("pause")` 문을 추가할 수 있습니다. 이 코드는 원래 일시 중지 프롬프트를 복제합니다.

1. C++ 코드에서는 `tanh` 메서드 내 첫 줄에서 중단점을 설정한 다음 디버거를 시작합니다. 해당 코드가 호출되면 디버거가 중지합니다.

    ![C++ 코드의 중단점에서 중지](media/cpp-debugging.png)

1. 이때 [C++ 및 Python을 함께 디버깅](debugging-mixed-mode.md)에 설명된 대로 C++ 코드를 단계별로 실행하고 변수를 검사하는 등의 작업을 수행할 수 있습니다.

## <a name="alternative-approaches"></a>대체 방법 

아래 표에 설명된 대로 다른 방법으로 Python 확장을 만들 수 있습니다. CPython에 대한 첫 번째 항목은 이 항목에서 이미 설명했습니다.

| 방법 | 연도 | 담당자 | 장점 | 단점 |
| --- | --- | --- | --- | --- |
| CPython용 C/C++ 확장 모듈 | 1991 | 표준 라이브러리 | [광범위한 설명서 및 자습서](https://docs.python.org/3/c-api/). 전체 제어. | 컴파일, 이식성, 참조 관리. 높은 C 지식. |
| SWIG | 1996 | [crfsuite](http://www.chokkan.org/software/crfsuite/) | 한 번에 여러 언어에 대한 바인딩 생성. | Python이 유일한 대상일 경우 과도한 오버헤드. |
| ctypes | 2003 | [oscrypto](https://github.com/wbond/oscrypto) | 컴파일 안 함, 광범위한 가용성. | 번거로운 C 구조체 액세스 및 변경과 오류 발생 가능성. |
| Cython | 2007 | [gevent](http://www.gevent.org/), [kivy](https://kivy.org/) | Python과 유사. 높은 완성도. 고성능. | 컴파일, 새 구문 및 도구 체인. |
| cffi | 2013 | [cryptography](https://cryptography.io/en/latest/), [pypy](http://pypy.org/) | 간편한 통합, PyPy 호환성. | 새로운 방법, 완성도 낮음. |

