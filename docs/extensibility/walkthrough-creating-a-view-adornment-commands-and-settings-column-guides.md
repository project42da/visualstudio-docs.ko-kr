---
title: "보기 장식, 명령 및 설정 만들기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4a2df0a3-42da-4f7b-996f-ee16a35ac922
caps.latest.revision: 7
ms.author: gregvanl
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: MT
ms.sourcegitcommit: 4a36302d80f4bc397128e3838c9abf858a0b5fe8
ms.openlocfilehash: c1836489b1845bca9e57daf83fc97bafeaf9da72
ms.contentlocale: ko-kr
ms.lasthandoff: 09/06/2017

---
# <a name="walkthrough-creating-a-view-adornment-commands-and-settings-column-guides"></a>연습: 보기 장식, 명령 및 설정 (열 안내선) 만들기
명령 및 효과 보기와 Visual Studio 텍스트/코드 편집기를 확장할 수 있습니다.  이 항목에서는 확장 인기 있는 기능을 사용 하면 열 안내선 시작 하는 방법을 보여 줍니다.  열 안내선 코드 특정 열 너비를 관리할 수 있도록 텍스트 편집기의 보기에 그려진 시각적으로 밝은 회선이 합니다.  구체적으로 서식이 지정 된 코드에 대 한 문서, 블로그 게시물을 포함 하거나 버그 보고서 예제 중요할 수 있습니다.  
  
 이 연습에서는 다음을 수행합니다.  
  
-   VSIX 프로젝트 만들기  
  
-   편집기 보기 adornment 추가  
  
-   저장 하 고 (여기서 그리기 열 안내선 및)에 게 해당 색상 설정 가져오기에 대 한 지원 추가  
  
-   명령을 추가 (안내선 열 추가/제거, 해당 색을 변경)  
  
-   편집 메뉴 및 텍스트 문서 상황에 맞는 메뉴에 명령을 배치합니다  
  
-   Visual Studio 명령 창에서 명령을 호출에 대 한 지원 추가  
  
 이 Visual Studio 갤러리와 열 안내선 기능의 버전을 수행 하려면[확장](https://visualstudiogallery.msdn.microsoft.com/da227a0b-0e31-4a11-8f6b-3a149cf2e459?SRC=Home)합니다.  
  
 **참고**:이 연습에서는 visual studio 확장 템플릿에 의해 생성 된 몇 개의 파일에 코드를 많이 붙여 하지만 곧이 연습에서는 참조 하는 확장 프로그램 예제가 포함 된 github의 완성 된 솔루션입니다.  완성 된 코드는 실제 명령 아이콘 generictemplate 아이콘을 사용 하는 대신 있다는 점에서 약간 다릅니다.  
  
## <a name="getting-started"></a>시작  
 Visual Studio 2015를 시작 하면 설치 하지 마십시오 Visual Studio SDK 다운로드 센터에서. Visual Studio 설치 프로그램에서 선택적 기능으로 포함 됩니다. 또한 VS SDK를 나중에 설치할 수 있습니다. 자세한 내용은 참조 [Visual Studio SDK 설치](../extensibility/installing-the-visual-studio-sdk.md)합니다.  
  
## <a name="setting-up-the-solution"></a>솔루션 설정  
 먼저 VSIX 프로젝트, 편집기 보기 adornment 추가 만들고 명령 (추가 하는 VSPackage를 소유할 명령)을 추가 합니다.  기본 아키텍처는 다음과 같습니다.  
  
-   텍스트 보기 만들기 수신기를 만드는 있는 `ColumnGuideAdornment` 뷰당 개체입니다.  이 개체는 뷰를 변경 하는 방법에 대 한 이벤트를 수신 하거나 필요에 따라 설정 변경, 업데이트 또는 다시 그리기 열 안내 합니다.  
  
-   한 `GuidesSettingsManager` Visual Studio 설정 저장소에서 읽기와 쓰기를 처리 하는 합니다.  설정 관리자 설정을 업데이트 하는 지 원하는 사용자 명령에 대 한 작업 역시 (열 추가, 열을 제거, 색 변경).  
  
-   필요한 경우 사용자 명령 VSIP 패키지는 이지만 명령을 구현 개체를 초기화 하는 상용구 코드만 합니다.  
  
-   한 `ColumnGuideCommands` .vsct 파일에 선언 된 사용자 명령을 구현 하는 명령에 대 한 명령 처리기를 연결 하는 개체입니다.  
  
 **VSIX**합니다.  사용 하 여 **파일 &#124; 새로운...**  프로젝트를 만들려면 명령입니다.  왼쪽된 탐색 창에서 C#에서 확장성 노드를 선택 하 고 선택 **VSIX 프로젝트** 오른쪽 창에서.  ColumnGuides 이름을 입력 하 고 선택 **확인** 프로젝트를 만듭니다.  
  
 **장식 볼**합니다.  솔루션 탐색기에서 프로젝트 노드를 오른쪽 포인터 단추를 눌러 합니다.  선택 된 **추가 &#124; 새 항목...**  명령을 새 보기 장식 항목을 추가 합니다.  선택 **확장성 &#124; 편집기** 왼쪽된 탐색 창에서 선택한 **편집기 뷰포트 장식** 오른쪽 창에서.  항목 이름으로 ColumnGuideAdornment 이름을 입력 하 고 선택 **추가** 추가 합니다.  
  
 이 항목 템플릿은 두 개의 파일 및에 추가 프로젝트 (뿐만 아니라 참조 등)을 볼 수 있습니다: ColumnGuideAdornment.cs 및 ColumnGuideAdornmentTextViewCreationListener.cs 합니다.  방금 템플릿 보기에 자주색 사각형을 그립니다.  다음 두 줄은 보기 만들기 수신기에서 변경 및 ColumnGuideAdornment.cs의 내용을 대체 합니다.  
  
 **명령**합니다.  솔루션 탐색기에서 프로젝트 노드를 오른쪽 포인터 단추를 눌러 합니다.  선택 된 **추가 &#124; 새 항목...**  명령을 새 보기 장식 항목을 추가 합니다.  선택 **확장성 &#124; VSPackage** 왼쪽된 탐색 창에서 선택한 **사용자 지정 명령** 오른쪽 창에서.  항목 이름으로 ColumnGuideCommands 이름을 입력 하 고 선택 **추가** 추가 합니다.  ColumnGuideCommands.cs, ColumnGuideCommandsPackage.cs, 및 ColumnGuideCommandsPackage.vsct 여러 개의 참조가 외에도 추가 명령 및 패키지를 추가 합니다.  다음 정의 하 고 명령을 구현 첫 번째 및 마지막 파일의 내용을 바꿉니다.  
  
## <a name="setting-up-the-text-view-creation-listener"></a>텍스트 보기 만들기 수신기를 설정  
 ColumnGuideAdornmentTextViewCreationListener.cs 편집기에서 엽니다.  이 코드는 때마다 Visual Studio 텍스트 뷰를 만듭니다에 대 한 처리기를 구현 합니다.  보기의 특성에 따라 처리기가 호출 하는 시기를 제어 하는 특성도 있습니다.  
  
 또한 코드는 표시 계층을 선언 해야 합니다.  편집기 뷰를 업데이트할 때 보기에 대 한 장식 레이어 가져옵니다를는 장식 요소를 가져옵니다.  특성을 가진 다른 사용자를 기준으로 계층의 순서를 선언할 수 있습니다.  다음 줄을 바꿉니다.  
  
```csharp  
[Order(After = PredefinedAdornmentLayers.Caret)]  
```  
  
 이러한 두 줄만 작성 합니다.  
  
```csharp  
[Order(Before = PredefinedAdornmentLayers.Text)]  
[TextViewRole(PredefinedTextViewRoles.Document)]  
```  
  
 교체는 표시 계층을 선언 하는 특성의 그룹에서입니다.   첫 번째 줄에서 열 가이드 선을 표시할 위치 변경 된 내용만 변경 했습니다.  선이 "전에" 보기에 텍스트 의미 뒤 또는 텍스트 아래에 나타납니다.  두 번째 줄은 열 가이드 장식을 문서, 프로그램 개념에 맞는 텍스트 엔터티를 적용할 수 있지만 편집 가능한 텍스트에 대 한 작업에 장식, 예를 들어 선언할 수 있습니다를 선언 합니다.  에 자세한 정보가 [언어 서비스 및 편집기 확장 지점](../extensibility/language-service-and-editor-extension-points.md)  
  
## <a name="implementing-the-settings-manager"></a>설정 관리자 구현  
 GuidesSettingsManager.cs의 내용을 아래에서 설명 하 고 다음 코드로 바꿉니다.  
  
```csharp  
using Microsoft.VisualStudio.Settings;  
using Microsoft.VisualStudio.Shell;  
using Microsoft.VisualStudio.Shell.Settings;  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
using System.Windows.Media;  
  
namespace ColumnGuides  
{  
    internal static class GuidesSettingsManager  
    {  
        // Because my code is always called from the UI thred, this succeeds.  
        internal static SettingsManager VsManagedSettingsManager =  
            new ShellSettingsManager(ServiceProvider.GlobalProvider);  
  
        private const int _maxGuides = 5;  
        private const string _collectionSettingsName = "Text Editor";  
        private const string _settingName = "Guides";  
        // 1000 seems reasonable since primary scenario is long lines of code  
        private const int _maxColumn = 1000;   
  
        static internal bool AddGuideline(int column)  
        {  
            if (! IsValidColumn(column))  
                throw new ArgumentOutOfRangeException(  
                    "column",  
                    "The paramenter must be between 1 and " + _maxGuides.ToString());  
            var offsets = GuidesSettingsManager.GetColumnOffsets();  
            if (offsets.Count() >= _maxGuides)  
                return false;  
            // Check for duplicates  
            if (offsets.Contains(column))  
                return false;  
            offsets.Add(column);  
            WriteSettings(GuidesSettingsManager.GuidelinesColor, offsets);  
            return true;  
        }  
  
        static internal bool RemoveGuideline(int column)  
        {  
            if (!IsValidColumn(column))  
                throw new ArgumentOutOfRangeException(  
                    "column", "The paramenter must be between 1 and 10,000");  
            var columns = GuidesSettingsManager.GetColumnOffsets();  
            if (! columns.Remove(column))  
            {  
                // Not present.  Allow user to remove the last column   
                // even if they're not on the right column.  
                if (columns.Count != 1)  
                    return false;  
  
                columns.Clear();  
            }  
            WriteSettings(GuidesSettingsManager.GuidelinesColor, columns);  
            return true;  
        }  
  
        static internal bool CanAddGuideline(int column)  
        {  
            if (!IsValidColumn(column))  
                return false;  
            var offsets = GetColumnOffsets();  
            if (offsets.Count >= _maxGuides)  
                return false;  
            return ! offsets.Contains(column);  
        }  
  
        static internal bool CanRemoveGuideline(int column)  
        {  
            if (! IsValidColumn(column))  
                return false;  
            // Allow user to remove the last guideline regardless of the column.  
            // Okay to call count, we limit the number of guides.  
            var offsets = GuidesSettingsManager.GetColumnOffsets();  
            return offsets.Contains(column) || offsets.Count() == 1;  
        }  
  
        static internal void RemoveAllGuidelines()  
        {  
            WriteSettings(GuidesSettingsManager.GuidelinesColor, new int[0]);  
        }  
  
        private static bool IsValidColumn(int column)  
        {  
            // zero is allowed (per user request)  
            return 0 <= column && column <= _maxColumn;  
        }  
  
        // This has format "RGB(<int>, <int>, <int>) <int> <int>...".  
        // There can be any number of ints following the RGB part,   
        // and each int is a column (char offset into line) where to draw.  
        static private string _guidelinesConfiguration;  
        static private string GuidelinesConfiguration  
        {  
            get  
            {  
                if (_guidelinesConfiguration == null)  
                {  
                    _guidelinesConfiguration =   
                        GetUserSettingsString(  
                            GuidesSettingsManager._collectionSettingsName,  
                            GuidesSettingsManager._settingName)  
                        .Trim();  
                }  
                return _guidelinesConfiguration;  
            }  
  
            set  
            {  
                if (value != _guidelinesConfiguration)  
                {  
                    _guidelinesConfiguration = value;  
                    WriteUserSettingsString(  
                        GuidesSettingsManager._collectionSettingsName,  
                        GuidesSettingsManager._settingName, value);  
                    // Notify ColumnGuideAdornments to update adornments in views.  
                    var handler = GuidesSettingsManager.SettingsChanged;  
                    if (handler != null)  
                        handler();  
                }  
            }  
        }  
  
        internal static string GetUserSettingsString(string collection, string setting)  
        {  
            var store = GuidesSettingsManager  
                            .VsManagedSettingsManager  
                            .GetReadOnlySettingsStore(SettingsScope.UserSettings);  
            return store.GetString(collection, setting, "RGB(255,0,0) 80");  
        }  
  
        internal static void WriteUserSettingsString(string key, string propertyName,  
                                                     string value)  
        {  
            var store = GuidesSettingsManager  
                            .VsManagedSettingsManager  
                            .GetWritableSettingsStore(SettingsScope.UserSettings);  
            store.CreateCollection(key);  
            store.SetString(key, propertyName, value);  
        }  
  
        // Persists settings and sets property with side effect of signaling  
        // ColumnGuideAdornments to update.  
        static private void WriteSettings(Color color, IEnumerable<int> columns)  
        {  
            string value = ComposeSettingsString(color, columns);  
            GuidelinesConfiguration = value;  
        }  
  
        private static string ComposeSettingsString(Color color,  
                                                    IEnumerable<int> columns)  
        {  
            StringBuilder sb = new StringBuilder();  
            sb.AppendFormat("RGB({0},{1},{2})", color.R, color.G, color.B);  
            IEnumerator<int> columnsEnumerator = columns.GetEnumerator();  
            if (columnsEnumerator.MoveNext())  
            {  
                sb.AppendFormat(" {0}", columnsEnumerator.Current);  
                while (columnsEnumerator.MoveNext())  
                {  
                    sb.AppendFormat(", {0}", columnsEnumerator.Current);  
                }  
            }  
            return sb.ToString();  
        }  
  
        // Parse a color out of a string that begins like "RGB(255,0,0)"  
        static internal Color GuidelinesColor  
        {  
            get  
            {  
                string config = GuidelinesConfiguration;  
                if (!String.IsNullOrEmpty(config) && config.StartsWith("RGB("))  
                {  
                    int lastParen = config.IndexOf(')');  
                    if (lastParen > 4)  
                    {  
                        string[] rgbs = config.Substring(4, lastParen - 4).Split(',');  
  
                        if (rgbs.Length >= 3)  
                        {  
                            byte r, g, b;  
                            if (byte.TryParse(rgbs[0], out r) &&  
                                byte.TryParse(rgbs[1], out g) &&  
                                byte.TryParse(rgbs[2], out b))  
                            {  
                                return Color.FromRgb(r, g, b);  
                            }  
                        }  
                    }  
                }  
                return Colors.DarkRed;  
            }  
  
            set  
            {  
                WriteSettings(value, GetColumnOffsets());  
            }  
        }  
  
        // Parse a list of integer values out of a string that looks like  
        // "RGB(255,0,0) 1, 5, 10, 80"  
        static internal List<int> GetColumnOffsets()  
        {  
            var result = new List<int>();  
            string settings = GuidesSettingsManager.GuidelinesConfiguration;  
            if (String.IsNullOrEmpty(settings))  
                return new List<int>();  
  
            if (!settings.StartsWith("RGB("))  
                return new List<int>();  
  
            int lastParen = settings.IndexOf(')');  
            if (lastParen <= 4)  
                return new List<int>();  
  
            string[] columns = settings.Substring(lastParen + 1).Split(',');  
  
            int columnCount = 0;  
            foreach (string columnText in columns)  
            {  
                int column = -1;  
                // VS 2008 gallery extension didn't allow zero, so per user request ...  
                if (int.TryParse(columnText, out column) && column >= 0)  
                {  
                    columnCount++;  
                    result.Add(column);  
                    if (columnCount >= _maxGuides)  
                        break;  
                }  
            }  
            return result;  
        }  
  
        // Delegate and Event to fire when settings change so that ColumnGuideAdornments   
        // can update.  We need nothing special in this event since the settings manager   
        // is statically available.  
        //  
        internal delegate void SettingsChangedHandler();  
        static internal event SettingsChangedHandler SettingsChanged;  
  
    }  
}  
  
```  
  
 이 코드의 대부분을 방금 만들고 설정을 형식을 구문 분석: "RGB (\<int >,\<int >,\<int >) \<int >, \<int >,...".  끝에 정수 열은 열 안내선을 원하는 위치 1부터 시작 열입니다.  열 안내선 확장 단일 설정 값 문자열에 해당 하는 모든 설정을 캡처합니다.  
  
 가치가 강조 표시 된 코드의 몇 가지 부분이 있습니다.  다음 코드 줄 설정 저장소에 대 한 Visual Studio의 관리 되는 래퍼를 가져옵니다.  대부분의 경우 Windows 레지스트리를 통해 추상화이 있지만이 API는 별개의 저장 메커니즘입니다.  
  
```csharp  
internal static SettingsManager VsManagedSettingsManager =  
    new ShellSettingsManager(ServiceProvider.GlobalProvider);  
```  
  
 Visual Studio 설정 저장소 모든 설정을 고유 하 게 식별 하는 범주 식별자와 설정 식별자를 사용 합니다.  
  
```csharp  
private const string _collectionSettingsName = "Text Editor";  
private const string _settingName = "Guides";  
```  
  
 사용할 필요가 없습니다 `"Text Editor"` 다음 category로 이름과 있습니다 중 선택할 수 필요 하면 합니다.  
  
 처음 몇 개의 함수는 설정을 변경할 수 있는 진입점입니다.  허용 되는 지침의 최대 수와 같은 개략적인 제약 조건을 확인 합니다.  다음은 호출 `WriteSettings` 설정 문자열을 작성 하 고 속성을 설정 하 `GuideLinesConfiguration`합니다.  Visual Studio 설정 저장소 및 화재에 설정 값을 저장이 속성을 설정는 `SettingsChanged` 모두 업데이트 하는 이벤트는 `ColumnGuideAdornment` 텍스트 보기와 연결 된 각 개체입니다.  
  
 와 같은 항목 지점 함수 중 몇 가지 `CanAddGuideline`, 설정을 변경 하는 명령을 구현 하는 데 사용 됩니다.  Visual Studio 메뉴에 표시 될 경우 명령 구현 하는 경우 명령이 현재 사용 되는지, 해당 이름이 무엇 인지 확인 하려면 등 쿼리 합니다.  다음 명령 구현에 대 한 이러한 진입점을 연결 하는 방법을 표시 됩니다.  참조 [확장 메뉴 및 명령을](../extensibility/extending-menus-and-commands.md) 명령에 대 한 자세한 내용은 합니다.  
  
## <a name="implementing-the-columnguideadornment-class"></a>ColumnGuideAdornment 클래스 구현  
 `ColumnGuideAdornment` 장식을 가질 수 있는 각 텍스트 보기에 대 한 클래스를 인스턴스화합니다.  이 클래스는 보기를 변경 하는 방법에 대 한 이벤트를 수신 하거나 필요에 따라 설정 변경, 업데이트 또는 다시 그리기 열 안내 합니다.  
  
 ColumnGuideAdornment.cs의 내용을 아래에서 설명 하 고 다음 코드로 바꿉니다.  
  
```csharp  
using System;  
using System.Windows.Media;  
using Microsoft.VisualStudio.Text.Editor;  
using System.Collections.Generic;  
using System.Windows.Shapes;  
using Microsoft.VisualStudio.Text.Formatting;  
using System.Windows;  
  
namespace ColumnGuides  
{  
    /// <summary>  
    /// Adornment class, one instance per text view that draws a guides on the viewport  
    /// </summary>  
    internal sealed class ColumnGuideAdornment  
    {  
        private const double _lineThickness = 1.0;  
        private IList<Line> _guidelines;  
        private IWpfTextView _view;  
        private double _baseIndentation;  
        private double _columnWidth;  
  
        /// <summary>  
        /// Creates editor column guidelines  
        /// </summary>  
        /// <param name="view">The <see cref="IWpfTextView"/> upon   
        /// which the adornment will be drawn</param>  
        public ColumnGuideAdornment(IWpfTextView view)  
        {  
            _view = view;  
            _guidelines = CreateGuidelines();  
            GuidesSettingsManager.SettingsChanged +=   
                new GuidesSettingsManager.SettingsChangedHandler(SettingsChanged);  
            view.LayoutChanged +=   
                new EventHandler<TextViewLayoutChangedEventArgs>(OnViewLayoutChanged);  
            _view.Closed += new EventHandler(OnViewClosed);  
        }  
  
        void SettingsChanged()  
        {  
            _guidelines = CreateGuidelines();  
            UpdatePositions();  
            AddGuidelinesToAdornmentLayer();  
        }  
  
        void OnViewClosed(object sender, EventArgs e)  
        {  
            _view.LayoutChanged -= OnViewLayoutChanged;  
            _view.Closed -= OnViewClosed;  
            GuidesSettingsManager.SettingsChanged -= SettingsChanged;  
        }  
  
        private bool _firstLayoutDone;  
  
        void OnViewLayoutChanged(object sender, TextViewLayoutChangedEventArgs e)  
        {  
            bool fUpdatePositions = false;  
  
            IFormattedLineSource lineSource = _view.FormattedLineSource;  
            if (lineSource == null)  
            {  
                return;  
            }  
            if (_columnWidth != lineSource.ColumnWidth)  
            {  
                _columnWidth = lineSource.ColumnWidth;  
                fUpdatePositions = true;  
            }  
            if (_baseIndentation != lineSource.BaseIndentation)  
            {  
                _baseIndentation = lineSource.BaseIndentation;  
                fUpdatePositions = true;  
            }  
            if (fUpdatePositions ||  
                e.VerticalTranslation ||  
                e.NewViewState.ViewportTop != e.OldViewState.ViewportTop ||  
                e.NewViewState.ViewportBottom != e.OldViewState.ViewportBottom)  
            {  
                UpdatePositions();  
            }  
            if (!_firstLayoutDone)  
            {  
                AddGuidelinesToAdornmentLayer();  
                _firstLayoutDone = true;  
            }  
        }  
  
        private static IList<Line> CreateGuidelines()  
        {  
            Brush lineBrush = new SolidColorBrush(GuidesSettingsManager.GuidelinesColor);  
            DoubleCollection dashArray = new DoubleCollection(new double[] { 1.0, 3.0 });  
            IList<Line> result = new List<Line>();  
            foreach (int column in GuidesSettingsManager.GetColumnOffsets())  
            {  
                Line line = new Line()  
                {  
                    // Use the DataContext slot as a cookie to hold the column  
                    DataContext = column,  
                    Stroke = lineBrush,  
                    StrokeThickness = _lineThickness,  
                    StrokeDashArray = dashArray  
                };  
                result.Add(line);  
            }  
            return result;  
        }  
  
        void UpdatePositions()  
        {  
            foreach (Line line in _guidelines)  
            {  
                int column = (int)line.DataContext;  
                line.X2 = _baseIndentation + 0.5 + column * _columnWidth;  
                line.X1 = line.X2;  
                line.Y1 = _view.ViewportTop;  
                line.Y2 = _view.ViewportBottom;  
            }  
        }  
  
        void AddGuidelinesToAdornmentLayer()  
        {  
            // Grab a reference to the adornment layer that this adornment   
            // should be added to  
            // Must match exported name in ColumnGuideAdornmentTextViewCreationListener  
            IAdornmentLayer adornmentLayer =   
                _view.GetAdornmentLayer("ColumnGuideAdornment");  
            if (adornmentLayer == null)  
                return;  
            adornmentLayer.RemoveAllAdornments();  
            // Add the guidelines to the adornment layer and make them relative   
            // to the viewport  
            foreach (UIElement element in _guidelines)  
                adornmentLayer.AddAdornment(AdornmentPositioningBehavior.OwnerControlled,  
                                            null, null, element, null);  
        }  
    }  
  
}  
```  
  
 이 클래스의 인스턴스는 연결 된 계속 <xref:Microsoft.VisualStudio.Text.Editor.IWpfTextView> 의 목록과 `Line` 보기에 그려진 개체입니다.  
  
 생성자 (에서 호출할 `ColumnGuideAdornmentTextViewCreationListener` Visual Studio 새 뷰를 생성할 때) 열 지침을 만들고 `Line` 개체입니다.  또한 생성자에 대 한 처리기를 추가 `SettingsChanged` 이벤트 (에 정의 된 `GuidesSettingsManager`) 및 이벤트 보기 `LayoutChanged` 및 `Closed`합니다.  
  
 `LayoutChanged` 다음과 같은 몇 가지 Visual Studio에서 보기를 만들 때를 포함 하는 보기의 변경 내용으로 인해 이벤트가 발생 합니다.  `OnViewLayoutChanged` 처리기 호출 `AddGuidelinesToAdornmentLayer` 실행할 수 있습니다.  코드 `OnViewLayoutChanged` 글꼴 크기를 변경, 보기 제본용, 가로 스크롤 등과 같은 변경 내용을 기반으로 하는 줄 위치를 업데이트 해야 합니다.  코드 `UpdatePositions` 문자 사이 또는 텍스트의 줄에 지정 된 문자 오프셋에 있는 텍스트의 열 바로 다음을 그릴 안내선 발생 합니다.  
  
 설정이 변경 될 때마다는 `SettingsChanged` 만 함수를 모두 다시 만듭니다는 `Line` 모든 새 설정을 사용 하 여 개체입니다.  코드 줄 위치를 설정한 후 이전의 모든 제거 `Line` 에서 개체는 `ColumnGuideAdornment` 표시 계층 새 파일로 추가 합니다.  
  
## <a name="defining-the-commands-menus-and-menu-placements"></a>명령, 메뉴 및 메뉴 위치를 정의합니다.  
 있을 수 있습니다 훨씬 명령 및 메뉴 선언, 다른 다양 한 메뉴에 명령 또는 메뉴 그룹에 배치 및 명령 처리기를 연결 합니다.  이 연습에서는이 확장에서 하지만 하위 수준 정보에 대 한 명령이 작동 하는 방법을 참조 하십시오. [확장 메뉴 및 명령을](../extensibility/extending-menus-and-commands.md)합니다.  
  
### <a name="introduction-to-the-code"></a>코드에 대 한 소개  
 열 안내선 확장 선언 명령에 속하는 그룹을 보여 줍니다 (열 추가, 열을 제거, 선 색 변경) 다음 편집기의 상황에 맞는 메뉴의 하위 메뉴에서 해당 그룹을 배치 합니다.  열 안내선 확장 명령을 주에도 추가 **편집** 메뉴 하지만 공간을 차지 하지 보이지 않는, 일반적인 패턴으로 설명 합니다.  
  
 명령 구현에 세 가지: ColumnGuideCommandsPackage.cs, ColumnGuideCommandsPackage.vsct, 및 ColumnGuideCommands.cs 합니다.  서식 파일에서 생성 된 코드에 명령을 배치는 **도구** 구현으로 대화 상자가 표시 되는 메뉴입니다.  구현 하는 방법을.vsct 및 ColumnGuideCommands.cs 파일에서 상당히 간단한 이므로 볼 수 있습니다.  아래 이러한 파일에 코드를 대체 됩니다.  
  
 패키지 코드는 Visual Studio 명령, 어디에 배치할지 명령 확장을 제공 한다는 검색에 필요한 상용구 선언 합니다.  패키지를 초기화 하는 경우 명령을 구현 클래스를 인스턴스화합니다.  명령에 관련 된 패키지에 대 한 자세한 내용은 위에 링크 명령을 참조 하십시오.  
  
### <a name="a-common-commands-pattern"></a>일반적인 명령 패턴  
 열 안내선 확장에서 주석은 Visual Studio의 매우 일반적인 패턴의 예입니다.  관련된 명령을 그룹에 배치 하 고 해당 그룹에 놓으면 주 메뉴에서 종종와 "`<CommandFlag>CommandWellOnly</CommandFlag>`" 명령은 표시 되지 않도록 설정 합니다.  주 메뉴에 명령을 배치 하는 (같은 **편집**) 이러한 방식으로 제공 좋은 이름 (같은 **Edit.AddColumnGuide**) 하는 키 바인딩에 다시 할당할 때 명령을 찾는 데 유용  **도구 옵션** 하 고 포함 된 명령을 호출할 때 완성을 가져오기 위한는 **명령 창**합니다.  
  
 다음 상황에 맞는 메뉴에 명령 그룹을 추가 하거나 하거나 하위 메뉴의 명령을 사용 하 여 사용자를 원하는 합니다.  Visual Studio에서 처리 `CommandWellOnly` 주 메뉴의 경우에 표시 안 함 플래그로 합니다.  상황에 맞는 메뉴 또는 하위 메뉴에 명령 같은 그룹을 배치할 때 명령이 표시 됩니다.  
  
 일반적인 패턴의 일부로 열 안내선 확장 단일 하위 메뉴를 포함 하는 두 번째 그룹을 만듭니다.  하위 메뉴는 차례로 4 개의 열 가이드 명령 사용 하 여 첫 번째 그룹을 포함합니다.  하위 메뉴를 포함 하는 두 번째 그룹은 다시 사용할 수 있는 자산 다양 한 상황에 맞는 메뉴에 배치 하는 이러한 상황에 맞는 메뉴에 하위 메뉴를 넣습니다.  
  
### <a name="the-vsct-file"></a>.Vsct 파일  
 .Vsct 파일 명령과 위치 이동, 아이콘과 함께 등을 선언 합니다.  .Vsct 파일의 내용을 아래에서 설명 하 고 다음 코드로 바꿉니다.  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<CommandTable xmlns="http://schemas.microsoft.com/VisualStudio/2005-10-18/CommandTable" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
  
  <!--  This is the file that defines the actual layout and type of the commands.  
        It is divided in different sections (e.g. command definition, command  
        placement, ...), with each defining a specific set of properties.  
        See the comment before each section for more details about how to  
        use it. -->  
  
  <!--  The VSCT compiler (the tool that translates this file into the binary  
        format that VisualStudio will consume) has the ability to run a preprocessor  
        on the vsct file; this preprocessor is (usually) the C++ preprocessor, so  
        it is possible to define includes and macros with the same syntax used  
        in C++ files. Using this ability of the compiler here, we include some files  
        defining some of the constants that we will use inside the file. -->  
  
  <!--This is the file that defines the IDs for all the commands exposed by   
      VisualStudio. -->  
  <Extern href="stdidcmd.h"/>  
  
  <!--This header contains the command ids for the menus provided by the shell. -->  
  <Extern href="vsshlids.h"/>  
  
  <!--The Commands section is where commands, menus, and menu groups are defined.  
      This section uses a Guid to identify the package that provides the command   
      defined inside it. -->  
  <Commands package="guidColumnGuideCommandsPkg">  
    <!-- Inside this section we have different sub-sections: one for the menus, another    
    for the menu groups, one for the buttons (the actual commands), one for the combos   
    and the last one for the bitmaps used. Each element is identified by a command id  
    that is a unique pair of guid and numeric identifier; the guid part of the identifier  
    is usually called "command set" and is used to group different command inside a  
    logically related group; your package should define its own command set in order to  
    avoid collisions with command ids defined by other packages. -->  
  
    <!-- In this section you can define new menu groups. A menu group is a container for   
         other menus or buttons (commands); from a visual point of view you can see the   
         group as the part of a menu contained between two lines. The parent of a group   
         must be a menu. -->  
    <Groups>  
  
      <!-- The main group is parented to the edit menu. All the buttons within the group  
           have the "CommandWellOnly" flag, so they're actually invisible, but it means  
           they get canonical names that begin with "Edit". Using placements, the group  
           is also placed in the GuidesSubMenu group. -->  
      <!-- The priority 0xB801 is chosen so it goes just after   
           IDG_VS_EDIT_COMMANDWELL -->  
      <Group guid="guidColumnGuidesCommandSet" id="GuidesMenuItemsGroup"  
             priority="0xB801">  
        <Parent guid="guidSHLMainMenu" id="IDM_VS_MENU_EDIT" />  
      </Group>  
  
      <!-- Group for holding the "Guidelines" sub-menu anchor (the item on the menu that  
           drops the sub menu). The group is parented to  
           the context menu for code windows. That takes care of most editors, but it's  
           also placed in a couple of other windows using Placements -->  
      <Group guid="guidColumnGuidesCommandSet" id="GuidesContextMenuGroup"   
             priority="0x0600">  
        <Parent guid="guidSHLMainMenu" id="IDM_VS_CTXT_CODEWIN" />  
      </Group>  
  
    </Groups>  
  
    <Menus>  
      <Menu guid="guidColumnGuidesCommandSet" id="GuidesSubMenu" priority="0x1000"  
            type="Menu">  
        <Parent guid="guidColumnGuidesCommandSet" id="GuidesContextMenuGroup" />  
        <Strings>  
          <ButtonText>&Column Guides</ButtonText>  
        </Strings>  
      </Menu>  
    </Menus>  
  
    <!--Buttons section. -->  
    <!--This section defines the elements the user can interact with, like a menu command or a button   
        or combo box in a toolbar. -->  
    <Buttons>  
      <!--To define a menu group you have to specify its ID, the parent menu and its   
          display priority.   
          The command is visible and enabled by default. If you need to change the   
          visibility, status, etc, you can use the CommandFlag node.  
          You can add more than one CommandFlag node e.g.:  
              <CommandFlag>DefaultInvisible</CommandFlag>  
              <CommandFlag>DynamicVisibility</CommandFlag>  
          If you do not want an image next to your command, remove the Icon node or   
          set it to <Icon guid="guidOfficeIcon" id="msotcidNoIcon" /> -->  
  
      <Button guid="guidColumnGuidesCommandSet" id="cmdidAddColumnGuide"   
              priority="0x0100" type="Button">  
        <Parent guid="guidColumnGuidesCommandSet" id="GuidesMenuItemsGroup" />  
        <Icon guid="guidImages" id="bmpPicAddGuide" />  
        <CommandFlag>CommandWellOnly</CommandFlag>  
        <CommandFlag>AllowParams</CommandFlag>  
        <Strings>  
          <ButtonText>&Add Column Guide</ButtonText>  
        </Strings>  
      </Button>  
  
      <Button guid="guidColumnGuidesCommandSet" id="cmdidRemoveColumnGuide"   
              priority="0x0101" type="Button">  
        <Parent guid="guidColumnGuidesCommandSet" id="GuidesMenuItemsGroup" />  
        <Icon guid="guidImages" id="bmpPicRemoveGuide" />  
        <CommandFlag>CommandWellOnly</CommandFlag>  
        <CommandFlag>AllowParams</CommandFlag>  
        <Strings>  
          <ButtonText>&Remove Column Guide</ButtonText>  
        </Strings>  
      </Button>  
  
      <Button guid="guidColumnGuidesCommandSet" id="cmdidChooseGuideColor"   
              priority="0x0103" type="Button">  
        <Parent guid="guidColumnGuidesCommandSet" id="GuidesMenuItemsGroup" />  
        <Icon guid="guidImages" id="bmpPicChooseColor" />  
        <CommandFlag>CommandWellOnly</CommandFlag>  
        <Strings>  
          <ButtonText>Column Guide &Color...</ButtonText>  
        </Strings>  
      </Button>  
  
      <Button guid="guidColumnGuidesCommandSet" id="cmdidRemoveAllColumnGuides"   
              priority="0x0102" type="Button">  
        <Parent guid="guidColumnGuidesCommandSet" id="GuidesMenuItemsGroup" />  
        <CommandFlag>CommandWellOnly</CommandFlag>  
        <Strings>  
          <ButtonText>Remove A&ll Columns</ButtonText>  
        </Strings>  
      </Button>  
    </Buttons>  
  
    <!--The bitmaps section is used to define the bitmaps that are used for the  
        commands.-->  
    <Bitmaps>  
      <!--  The bitmap id is defined in a way that is a little bit different from the  
            others:   
            the declaration starts with a guid for the bitmap strip, then there is the  
            resource id of the bitmap strip containing the bitmaps and then there are   
            the numeric ids of the elements used inside a button definition. An important  
            aspect of this declaration is that the element id   
            must be the actual index (1-based) of the bitmap inside the bitmap strip. -->  
      <Bitmap guid="guidImages" href="Resources\ColumnGuideCommands.png"   
              usedList="bmpPicAddGuide, bmpPicRemoveGuide, bmpPicChooseColor" />  
    </Bitmaps>  
  
  </Commands>  
  
  <CommandPlacements>  
  
    <!-- Define secondary placements for our groups -->  
  
    <!-- Place the group containing the three commands in the sub-menu -->  
    <CommandPlacement guid="guidColumnGuidesCommandSet" id="GuidesMenuItemsGroup"   
                      priority="0x0100">  
      <Parent guid="guidColumnGuidesCommandSet" id="GuidesSubMenu" />  
    </CommandPlacement>  
  
    <!-- The HTML editor context menu, for some reason, redefines its own groups  
         so we need to place a copy of our context menu there too. -->  
    <CommandPlacement guid="guidColumnGuidesCommandSet" id="GuidesContextMenuGroup"   
                      priority="0x1001">  
      <Parent guid="CMDSETID_HtmEdGrp" id="IDMX_HTM_SOURCE_HTML" />  
    </CommandPlacement>  
  
    <!-- The HTML context menu in Dev12 changed. -->  
    <CommandPlacement guid="guidColumnGuidesCommandSet" id="GuidesContextMenuGroup"   
                      priority="0x1001">  
      <Parent guid="CMDSETID_HtmEdGrp_Dev12" id="IDMX_HTM_SOURCE_HTML_Dev12" />  
    </CommandPlacement>  
  
    <!-- Similarly for Script -->  
    <CommandPlacement guid="guidColumnGuidesCommandSet" id="GuidesContextMenuGroup"  
                      priority="0x1001">  
      <Parent guid="CMDSETID_HtmEdGrp" id="IDMX_HTM_SOURCE_SCRIPT" />  
    </CommandPlacement>  
  
    <!-- Similarly for ASPX  -->  
    <CommandPlacement guid="guidColumnGuidesCommandSet" id="GuidesContextMenuGroup"   
                      priority="0x1001">  
      <Parent guid="CMDSETID_HtmEdGrp" id="IDMX_HTM_SOURCE_ASPX" />  
    </CommandPlacement>  
  
    <!-- Similarly for the XAML editor context menu -->  
    <CommandPlacement guid="guidColumnGuidesCommandSet" id="GuidesContextMenuGroup"  
                      priority="0x0600">  
      <Parent guid="guidXamlUiCmds" id="IDM_XAML_EDITOR" />  
    </CommandPlacement>  
  
  </CommandPlacements>  
  
  <!-- This defines the identifiers and their values used above to index resources  
       and specify commands. -->  
  <Symbols>  
    <!-- This is the package guid. -->  
    <GuidSymbol name="guidColumnGuideCommandsPkg"   
                value="{e914e5de-0851-4904-b361-1a3a9d449704}" />  
  
    <!-- This is the guid used to group the menu commands together -->  
    <GuidSymbol name="guidColumnGuidesCommandSet"   
                value="{c2bc0047-8bfa-4e5a-b5dc-45af8c274d8e}">  
      <IDSymbol name="GuidesContextMenuGroup" value="0x1020" />  
      <IDSymbol name="GuidesMenuItemsGroup" value="0x1021" />  
      <IDSymbol name="GuidesSubMenu" value="0x1022" />  
      <IDSymbol name="cmdidAddColumnGuide" value="0x0100" />  
      <IDSymbol name="cmdidRemoveColumnGuide" value="0x0101" />  
      <IDSymbol name="cmdidChooseGuideColor" value="0x0102" />  
      <IDSymbol name="cmdidRemoveAllColumnGuides" value="0x0103" />  
    </GuidSymbol>  
  
    <GuidSymbol name="guidImages" value="{2C99F852-587C-43AF-AA2D-F605DE2E46EF}">  
      <IDSymbol name="bmpPicAddGuide" value="1" />  
      <IDSymbol name="bmpPicRemoveGuide" value="2" />  
      <IDSymbol name="bmpPicChooseColor" value="3" />  
    </GuidSymbol>  
  
    <GuidSymbol name="CMDSETID_HtmEdGrp_Dev12"   
                value="{78F03954-2FB8-4087-8CE7-59D71710B3BB}">  
      <IDSymbol name="IDMX_HTM_SOURCE_HTML_Dev12" value="0x1" />  
    </GuidSymbol>  
  
    <GuidSymbol name="CMDSETID_HtmEdGrp" value="{d7e8c5e1-bdb8-11d0-9c88-0000f8040a53}">  
      <IDSymbol name="IDMX_HTM_SOURCE_HTML" value="0x33" />  
      <IDSymbol name="IDMX_HTM_SOURCE_SCRIPT" value="0x34" />  
      <IDSymbol name="IDMX_HTM_SOURCE_ASPX" value="0x35" />  
    </GuidSymbol>  
  
    <GuidSymbol name="guidXamlUiCmds" value="{4c87b692-1202-46aa-b64c-ef01faec53da}">  
      <IDSymbol name="IDM_XAML_EDITOR" value="0x103" />  
    </GuidSymbol>  
  </Symbols>  
  
</CommandTable>  
  
```  
  
 **GUID**합니다.  명령 처리기를 찾아 호출할 Visual Studio에 대 한 GUID (위쪽에서 복사한.vsct 파일에 선언 된 패키지를 일치 하는 GUID (프로젝트 항목 템플릿에서 생성) ColumnGuideCommandsPackage.cs 파일에 선언 된 패키지를 확인 해야 ).  이 샘플 코드를 다시 사용 하는 경우이 코드에 복사한 있는 다른 모든 사용자와 충돌 하지 않는 다른 GUID가 있는지 확인 해야 합니다.  
  
 ColumnGuideCommandsPackage.cs에서이 줄을 찾아 따옴표 사이 있는 GUID 복사:  
  
```csharp  
public const string PackageGuidString = "ef726849-5447-4f73-8de5-01b9e930f7cd";  
```  
  
 다음 GUID를 붙여 넣습니다.vsct 파일에 있는 다음 줄 프로그램 `Symbols` 선언 합니다.  
  
```xml  
<GuidSymbol name="guidColumnGuideCommandsPkg"   
            value="{ef726849-5447-4f73-8de5-01b9e930f7cd}" />  
```  
  
 명령에 대 한 guid가 설정 하 고 비트맵 이미지 파일 너무 확장 프로그램에 대해 고유 해야 합니다.  
  
```xml  
<GuidSymbol name="guidColumnGuidesCommandSet"   
            value="{c2bc0047-8bfa-4e5a-b5dc-45af8c274d8e}">  
<GuidSymbol name="guidImages" value="{2C99F852-587C-43AF-AA2D-F605DE2E46EF}">  
```  
  
 그러나 명령 집합을 변경 하 고이 연습에서 작동 하도록 코드를 가져오는 이미지 Guid 비트맵 필요가 없습니다.  명령은 ColumnGuideCommands.cs 파일의 선언과 일치 해야 하는 GUID를 설정할 수 있지만 그 파일의 내용을 너무; 대체할 예정 따라서 Guid 일치 합니다.  
  
 .Vsct 파일에서 다른 Guid 열 가이드 명령을 추가 되는 기존 메뉴 식별 변경할 수는 없습니다.  
  
 **파일 섹션**합니다.  .Vsct 외부 섹션이 3: 명령, 배치 및 기호입니다.  Commands 섹션에서는 명령 그룹, 메뉴, 단추 또는 메뉴 항목 및 아이콘에 대 한 비트맵을 정의합니다.  배치 섹션 그룹 메뉴 또는 기존 메뉴에 추가 위치에 어디로 선언 합니다.  기호 섹션 하면.vsct 코드 보다 Guid 및 16 진수로 everywhere 것 보다 읽기 쉬운.vsct 파일의 다른 곳에서 사용 되는 식별자를 선언 합니다.  
  
 **섹션 명령, 그룹 정의**합니다.  먼저 commands 섹션에서는 명령 그룹을 정의합니다.  명령 그룹은 그룹을 구분 하는 약간의 회색 선으로 메뉴에 표시 되는 명령입니다.  그룹 수도이 예제와 같이 전체 하위 메뉴에서 채운 표시 되지 않으면이 경우 줄을 구분 하는 회색으로 표시 합니다.  .Vsct 파일 선언 두 그룹의 `GuidesMenuItemsGroup` 부모가 되는 `IDM_VS_MENU_EDIT` (주 **편집** 메뉴) 및 `GuidesContextMenuGroup` 부모가 되는 `IDM_VS_CTXT_CODEWIN` (코드 편집기의 상황에 맞는 메뉴).  
  
 두 번째 그룹 선언에는 `0x0600` 우선 순위:  
  
```xml  
<Group guid="guidColumnGuidesCommandSet" id="GuidesContextMenuGroup"   
             priority="0x0600">  
```  
  
 이 아이디어는 열을 배치 하는 상황에 맞는 메뉴의 하위 메뉴 그룹 추가 후에 하위 메뉴 과정을 안내 합니다.  그러나 가정 하지 않아야 가장 잘 알고 있고 하위 메뉴의 우선 순위를 사용 하 여 마지막은 항상를 강제로 `0xFFFF`합니다.  이 숫자 어디에 배치 하는 상황에 맞는 메뉴에 하위 메뉴에 있는 위치 참조를 활용 하 여 해야 합니다.  이 경우 `0x0600` 값이 너무 커서 관련해 서 볼 수 있지만 문제가 있는 경우는 열 안내선 확장 보다 낮을 수에 해당 확장을 디자인 하는 다른 사용자를 위한 공간을 벗어나 메뉴의 끝에 배치 합니다.  
  
 **명령 메뉴 정의 섹션**합니다.  명령 섹션 하위 메뉴를 정의 하는 다음 `GuidesSubMenu`부모가는 `GuidesContextMenuGroup`합니다.  `GuidesContextMenuGroup` 모든 관련 상황에 맞는 메뉴에 추가 하는 그룹입니다.  배치 섹션 코드가 하위 메뉴에서 4 개의 열 가이드 명령 사용 하 여 그룹을 배치합니다.  
  
 **섹션 명령, 정의 단추**합니다.  Commands 섹션에서는 다음 메뉴 항목을 정의 또는 4 개의 열이 되는 단추 명령을 안내 합니다.  `CommandWellOnly`위에서 설명한 명령은 주 메뉴에 했을 때 표시 되지 않습니다.을 의미 합니다.  메뉴 항목의 2 단추 선언 선 추가 및 제거 가이드도는 `AllowParams` 플래그:  
  
```xml  
<CommandFlag>AllowParams</CommandFlag>  
```  
  
 이 플래그를 Visual Studio 명령 처리기를 호출 하는 경우 인수를 받을 명령 주 메뉴 내의 위치를 갖는 함께 있습니다.  명령 창에서 명령을 호출 하는 사용자를 가져옵니다 전달 되는 인수 명령 처리기를 이벤트 인수입니다.  
  
 **명령을 섹션, 비트맵 정의**합니다.  마지막으로 commands 섹션에서는 비트맵 또는 명령에 사용 되는 아이콘을 선언 합니다.  프로젝트 리소스를 식별 하 고 사용 되는 아이콘의 인덱스 1부터 나열 하는 단순한 선언입니다.  .Vsct 파일의 기호 섹션 인덱스로 사용 되는 식별자의 값을 선언 합니다.  이 연습에서는 프로젝트에 추가 사용자 지정 명령 항목 템플릿과 함께 제공 되는 비트맵 스트립을 사용 합니다.  
  
 **배치 섹션**합니다.  명령 다음 섹션은 배치 섹션입니다.  첫 번째는 여기서 추가 코드는 위에서 설명한 첫 번째 그룹 보유 4 개의 열이 가이드는 하위 메뉴에 명령을 명령을 표시 하는 위치입니다.  
  
```xml  
<CommandPlacement guid="guidColumnGuidesCommandSet" id="GuidesMenuItemsGroup"   
                  priority="0x0100">  
  <Parent guid="guidColumnGuidesCommandSet" id="GuidesSubMenu" />  
</CommandPlacement>  
```  
  
 다른 배치에 대 한 모든 추가 `GuidesContextMenuGroup` (포함 하는 `GuidesSubMenu`) 다른 편집기 상황에 맞는 메뉴에 있습니다.  코드는 선언 하는 경우는 `GuidesContextMenuGroup`, 코드 편집기의 상황에 맞는 메뉴 부모로 지정 되었습니다.  이 코드 편집기의 상황에 맞는 메뉴에 대 한 배치 표시 되지 않으면 때문입니다.  
  
 **섹션의 기호**합니다.  위에서 설명 했 듯이 기호 섹션 하면.vsct 코드 보다 Guid 및 16 진수로 everywhere 것 보다 읽기 쉬운.vsct 파일의 다른 곳에서 사용 되는 식별자를 선언 합니다.  이 섹션의 중요 한 사항은 패키지 GUID 명령 구현 클래스에서 선언 된 GUID 일치 해야 하는 패키지 클래스 및 명령 집합의 선언에 동의 해야 합니다.  
  
## <a name="implementing-the-commands"></a>명령을 구현합니다.  
 ColumnGuideCommands.cs 파일 명령을 구현 하 고 처리기를 연결 합니다.  Visual Studio 패키지를 로드 및 초기화 하는 경우 패키지 호출 하 여 `Initialize` 명령 구현 클래스에 있습니다.  단순히 명령을 초기화를 사용 하는 클래스를 인스턴스화하고 생성자는 모든 명령 처리기를 연결 합니다.  
  
 ColumnGuideCommands.cs 파일의 내용을 아래에서 설명 하 고 다음 코드로 바꿉니다.  
  
```csharp  
using System;  
using System.ComponentModel.Design;  
using System.Globalization;  
using Microsoft.VisualStudio.Shell;  
using Microsoft.VisualStudio.Shell.Interop;  
using Microsoft.VisualStudio.TextManager.Interop;  
using Microsoft.VisualStudio.Text.Editor;  
using Microsoft.VisualStudio;  
  
namespace ColumnGuides  
{  
    /// <summary>  
    /// Command handler  
    /// </summary>  
    internal sealed class ColumnGuideCommands  
    {  
  
        const int cmdidAddColumnGuide = 0x0100;  
        const int cmdidRemoveColumnGuide = 0x0101;  
        const int cmdidChooseGuideColor = 0x0102;  
        const int cmdidRemoveAllColumnGuides = 0x0103;  
  
        /// <summary>  
        /// Command menu group (command set GUID).  
        /// </summary>  
        static readonly Guid CommandSet =   
            new Guid("c2bc0047-8bfa-4e5a-b5dc-45af8c274d8e");  
  
        /// <summary>  
        /// VS Package that provides this command, not null.  
        /// </summary>  
        private readonly Package package;  
  
        OleMenuCommand _addGuidelineCommand;  
        OleMenuCommand _removeGuidelineCommand;  
  
        /// <summary>  
        /// Initializes the singleton instance of the command.  
        /// </summary>  
        /// <param name="package">Owner package, not null.</param>  
        public static void Initialize(Package package)  
        {  
            Instance = new ColumnGuideCommands(package);  
        }  
  
        /// <summary>  
        /// Gets the instance of the command.  
        /// </summary>  
        public static ColumnGuideCommands Instance  
        {  
            get;  
            private set;  
        }  
  
        /// <summary>  
        /// Initializes a new instance of the <see cref="ColumnGuideCommands"/> class.  
        /// Adds our command handlers for menu (commands must exist in the command   
        /// table file)  
        /// </summary>  
        /// <param name="package">Owner package, not null.</param>  
        private ColumnGuideCommands(Package package)  
        {  
            if (package == null)  
            {  
                throw new ArgumentNullException("package");  
            }  
  
            this.package = package;  
  
            // Add our command handlers for menu (commands must exist in the .vsct file)  
  
            OleMenuCommandService commandService =  
                this.ServiceProvider.GetService(typeof(IMenuCommandService))  
                    as OleMenuCommandService;  
            if (commandService != null)  
            {  
                // Add guide  
                _addGuidelineCommand =   
                    new OleMenuCommand(AddColumnGuideExecuted, null,  
                                       AddColumnGuideBeforeQueryStatus,  
                                       new CommandID(ColumnGuideCommands.CommandSet,  
                                                     cmdidAddColumnGuide));  
                _addGuidelineCommand.ParametersDescription = "<column>";  
                commandService.AddCommand(_addGuidelineCommand);  
                // Remove guide  
                _removeGuidelineCommand =  
                    new OleMenuCommand(RemoveColumnGuideExecuted, null,  
                                       RemoveColumnGuideBeforeQueryStatus,  
                                       new CommandID(ColumnGuideCommands.CommandSet,  
                                                     cmdidRemoveColumnGuide));  
                _removeGuidelineCommand.ParametersDescription = "<column>";  
                commandService.AddCommand(_removeGuidelineCommand);  
                // Choose color  
                commandService.AddCommand(  
                    new MenuCommand(ChooseGuideColorExecuted,  
                                    new CommandID(ColumnGuideCommands.CommandSet,  
                                                  cmdidChooseGuideColor)));  
                // Remove all  
                commandService.AddCommand(  
                    new MenuCommand(RemoveAllGuidelinesExecuted,  
                                    new CommandID(ColumnGuideCommands.CommandSet,  
                                                  cmdidRemoveAllColumnGuides)));  
            }  
        }  
  
        /// <summary>  
        /// Gets the service provider from the owner package.  
        /// </summary>  
        private IServiceProvider ServiceProvider  
        {  
            get  
            {  
                return this.package;  
            }  
        }  
  
        private void AddColumnGuideBeforeQueryStatus(object sender, EventArgs e)  
        {  
            int currentColumn = GetCurrentEditorColumn();  
            _addGuidelineCommand.Enabled =  
                GuidesSettingsManager.CanAddGuideline(currentColumn);  
        }  
  
        private void RemoveColumnGuideBeforeQueryStatus(object sender, EventArgs e)  
        {  
            int currentColumn = GetCurrentEditorColumn();  
            _removeGuidelineCommand.Enabled =  
                GuidesSettingsManager.CanRemoveGuideline(currentColumn);  
        }  
  
        private int GetCurrentEditorColumn()  
        {  
            IVsTextView view = GetActiveTextView();  
            if (view == null)  
            {  
                return -1;  
            }  
  
            try  
            {  
                IWpfTextView textView = GetTextViewFromVsTextView(view);  
                int column = GetCaretColumn(textView);  
  
                // Note: GetCaretColumn returns 0-based positions. Guidelines are 1-based  
                // positions.  
                // However, do not subtract one here since the caret is positioned to the  
                // left of  
                // the given column and the guidelines are positioned to the right. We  
                // want the  
                // guideline to line up with the current caret position. e.g. When the  
                // caret is  
                // at position 1 (zero-based), the status bar says column 2. We want to  
                // add a  
                // guideline for column 1 since that will place the guideline where the  
                // caret is.  
                return column;  
            }  
            catch (InvalidOperationException)  
            {  
                return -1;  
            }  
        }  
  
        /// <summary>  
        /// Find the active text view (if any) in the active document.  
        /// </summary>  
        /// <returns>The IVsTextView of the active view, or null if there is no active  
        /// document or the  
        /// active view in the active document is not a text view.</returns>  
        private IVsTextView GetActiveTextView()  
        {  
            IVsMonitorSelection selection =  
                this.ServiceProvider.GetService(typeof(IVsMonitorSelection))  
                                                    as IVsMonitorSelection;  
            object frameObj = null;  
            ErrorHandler.ThrowOnFailure(  
                selection.GetCurrentElementValue(  
                    (uint)VSConstants.VSSELELEMID.SEID_DocumentFrame, out frameObj));  
  
            IVsWindowFrame frame = frameObj as IVsWindowFrame;  
            if (frame == null)  
            {  
                return null;  
            }  
  
            return GetActiveView(frame);  
        }  
  
        private static IVsTextView GetActiveView(IVsWindowFrame windowFrame)  
        {  
            if (windowFrame == null)  
            {  
                throw new ArgumentException("windowFrame");  
            }  
  
            object pvar;  
            ErrorHandler.ThrowOnFailure(  
                windowFrame.GetProperty((int)__VSFPROPID.VSFPROPID_DocView, out pvar));  
  
            IVsTextView textView = pvar as IVsTextView;  
            if (textView == null)  
            {  
                IVsCodeWindow codeWin = pvar as IVsCodeWindow;  
                if (codeWin != null)  
                {  
                    ErrorHandler.ThrowOnFailure(codeWin.GetLastActiveView(out textView));  
                }  
            }  
            return textView;  
        }  
  
        private static IWpfTextView GetTextViewFromVsTextView(IVsTextView view)  
        {  
  
            if (view == null)  
            {  
                throw new ArgumentNullException("view");  
            }  
  
            IVsUserData userData = view as IVsUserData;  
            if (userData == null)  
            {  
                throw new InvalidOperationException();  
            }  
  
            object objTextViewHost;  
            if (VSConstants.S_OK  
                   != userData.GetData(Microsoft.VisualStudio  
                                                .Editor  
                                                .DefGuidList.guidIWpfTextViewHost,  
                                       out objTextViewHost))  
            {  
                throw new InvalidOperationException();  
            }  
  
            IWpfTextViewHost textViewHost = objTextViewHost as IWpfTextViewHost;  
            if (textViewHost == null)  
            {  
                throw new InvalidOperationException();  
            }  
  
            return textViewHost.TextView;  
        }  
  
        /// <summary>  
        /// Given an IWpfTextView, find the position of the caret and report its column  
        /// number. The column number is 0-based  
        /// </summary>  
        /// <param name="textView">The text view containing the caret</param>  
        /// <returns>The column number of the caret's position. When the caret is at the  
        /// leftmost column, the return value is zero.</returns>  
        private static int GetCaretColumn(IWpfTextView textView)  
        {  
            // This is the code the editor uses to populate the status bar.  
            Microsoft.VisualStudio.Text.Formatting.ITextViewLine caretViewLine =  
                textView.Caret.ContainingTextViewLine;  
            double columnWidth = textView.FormattedLineSource.ColumnWidth;  
            return (int)(Math.Round((textView.Caret.Left - caretViewLine.Left)  
                                       / columnWidth));  
        }  
  
        /// <summary>  
        /// Determine the applicable column number for an add or remove command.  
        /// The column is parsed from command arguments, if present. Otherwise  
        /// the current position of the caret is used to determine the column.  
        /// </summary>  
        /// <param name="e">Event args passed to the command handler.</param>  
        /// <returns>The column number. May be negative to indicate the column number is  
        /// unavailable.</returns>  
        /// <exception cref="ArgumentException">The column number parsed from event args  
        /// was not a valid integer.</exception>  
        private int GetApplicableColumn(EventArgs e)  
        {  
            var inValue = ((OleMenuCmdEventArgs)e).InValue as string;  
            if (!string.IsNullOrEmpty(inValue))  
            {  
                int column;  
                if (!int.TryParse(inValue, out column) || column < 0)  
                    throw new ArgumentException("Invalid column");  
                return column;  
            }  
  
            return GetCurrentEditorColumn();  
        }  
  
        /// <summary>  
        /// This function is the callback used to execute a command when the a menu item  
        /// is clicked. See the Initialize method to see how the menu item is associated  
        /// to this function using the OleMenuCommandService service and the MenuCommand  
        /// class.  
        /// </summary>  
        private void AddColumnGuideExecuted(object sender, EventArgs e)  
        {  
            int column = GetApplicableColumn(e);  
            if (column >= 0)  
            {  
                GuidesSettingsManager.AddGuideline(column);  
            }  
        }  
  
        private void RemoveColumnGuideExecuted(object sender, EventArgs e)  
        {  
            int column = GetApplicableColumn(e);  
            if (column >= 0)  
            {  
                GuidesSettingsManager.RemoveGuideline(column);  
            }  
        }  
  
        private void RemoveAllGuidelinesExecuted(object sender, EventArgs e)  
        {  
            GuidesSettingsManager.RemoveAllGuidelines();  
        }  
  
        private void ChooseGuideColorExecuted(object sender, EventArgs e)  
        {  
            System.Windows.Media.Color color = GuidesSettingsManager.GuidelinesColor;  
  
            using (System.Windows.Forms.ColorDialog picker =   
                new System.Windows.Forms.ColorDialog())  
            {  
                picker.Color = System.Drawing.Color.FromArgb(255, color.R, color.G,  
                                                             color.B);  
                if (picker.ShowDialog() == System.Windows.Forms.DialogResult.OK)  
                {  
                    GuidesSettingsManager.GuidelinesColor =   
                        System.Windows.Media.Color.FromRgb(picker.Color.R,  
                                                           picker.Color.G,   
                                                           picker.Color.B);  
                }  
            }  
        }  
  
    }  
}  
  
```  
  
 **참조를 수정**합니다.  이 시점에서 대 한 참조를 요소가 없습니다.  솔루션 탐색기에서 참조 노드 오른쪽 포인터 단추를 누르면 됩니다.  선택 된 **추가...**  명령입니다.  **참조 추가** 대화 상자에 검색 상자 오른쪽 위 모서리에 있습니다.  (큰따옴표) 없이 "편집기" 입력 합니다.  선택 된 **Microsoft.VisualStudio.Editor** (해야 상자를 선택 하지 선택 항목의 왼쪽에 있는 항목) 항목 선택 **확인** 참조를 추가 합니다.  
  
 **초기화**합니다.  패키지 클래스를 초기화 하는 경우 호출 `Initialize` 명령 구현 클래스에 있습니다.  `ColumnGuideCommands` 초기화는 클래스를 인스턴스화 및 클래스 멤버에 클래스 인스턴스 및 패키지 파일에 대 한 참조를 저장 합니다.  
  
 클래스 생성자에서 명령 처리기 후크 ups 중 하나에 대해 살펴보겠습니다.  
  
```csharp  
_addGuidelineCommand =   
    new OleMenuCommand(AddColumnGuideExecuted, null,  
                       AddColumnGuideBeforeQueryStatus,  
                       new CommandID(ColumnGuideCommands.CommandSet,  
                                     cmdidAddColumnGuide));  
  
```  
  
 만들 프로그램 `OleMenuCommand`합니다.  Visual Studio는 Microsoft Office 명령 시스템을 사용합니다.  Key 인수는 OleMenuCommand 인스턴스화할 때 명령을 구현 하는 함수 (`AddColumnGuideExecuted`), Visual Studio 명령 사용 하 여 메뉴를 표시 하는 때 호출할 함수 (`AddColumnGuideBeforeQueryStatus`), 및 명령 id입니다.  Visual studio 명령 보이지 않거나 메뉴의 특정 디스플레이 대 한 회색 자체 내릴 수 있도록 명령을 메뉴에 표시 하기 전에 쿼리 상태 함수 호출 (예를 들어 사용 하지 않도록 설정 **복사** 선택 영역이 없는 경우), 해당 아이콘을 변경 하거나도 해당 이름 (예를 들어에서 추가를 제거)을 변경 하 고 등입니다.  명령 ID에는.vsct 파일에 선언 된 명령 ID와 일치 해야 합니다.  명령에 대 한 문자열 설정 하 고 열 안내선 추가 명령을.vsct 파일 및는 ColumnGuideCommands.cs 간에 일치 해야 합니다.  
  
 다음 줄에서는 사용자가 아래에서 설명 하 고 명령 창을 통해 명령을 호출에 대 한 지원을 제공 합니다.  
  
```csharp  
_addGuidelineCommand.ParametersDescription = "<column>";  
```  
  
 **상태를 쿼리**합니다.  쿼리 상태 함수 `AddColumnGuideBeforeQueryStatus` 및 `RemoveColumnGuideBeforeQueryStatus` 몇 가지 설정 (예: 최대 수 가이드 또는 최대 열)을 확인 하거나 제거 하는 열 가이드가 경우.  명령을 사용 조건에 맞는 올바른 경우 있습니다.  Visual Studio 메뉴에서 각 명령에 대 한 메뉴는 표시 될 때마다 실행 되기 때문에 매우 효율적으로 쿼리 상태 함수에 필요 합니다.  
  
 **AddColumnGuideExecuted 함수**합니다.  추가 가이드의 흥미로운 부분은 현재 편집기 보기 및 캐럿 위치를 파악 합니다.  이 함수는 먼저 호출 `GetApplicableColumn` 에서는 사용자가 제공한 인수에에서 없는 명령 처리기의 이벤트 인수를 확인 하 고 없는 경우, 다음 함수는 편집기의 뷰에서 검사 합니다.  
  
```csharp  
private int GetApplicableColumn(EventArgs e)  
{  
    var inValue = ((OleMenuCmdEventArgs)e).InValue as string;  
    if (!string.IsNullOrEmpty(inValue))  
    {  
        int column;  
        if (!int.TryParse(inValue, out column) || column < 0)  
            throw new ArgumentException("Invalid column");  
        return column;  
    }  
  
    return GetCurrentEditorColumn();  
}  
  
```  
  
 `GetCurrentEditorColumn`가져올 자세히 파일에 <xref:Microsoft.VisualStudio.Text.Editor.IWpfTextView> 코드의 보기입니다.  통해 추적 하는 경우 `GetActiveTextView`, `GetActiveView`, 및 `GetTextViewFromVsTextView`, 작업을 수행 하는 방법을 알 수 있습니다.  다음 관련 코드는 추상적 현재 선택 항목으로 시작을 차례로 선택의 프레임을 가져오기으로 프레임의 문서 뷰 가져오기는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView>, 한 다음 가져와 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsUserData> 뷰 호스트 가져오기 IVsTextView에서 및 마지막으로 IWpfTextView:  
  
```csharp  
   IVsMonitorSelection selection =  
       this.ServiceProvider.GetService(typeof(IVsMonitorSelection))   
           as IVsMonitorSelection;  
   object frameObj = null;  
  
ErrorHandler.ThrowOnFailure(selection.GetCurrentElementValue(  
                                (uint)VSConstants.VSSELELEMID.SEID_DocumentFrame,  
                                out frameObj));  
  
   IVsWindowFrame frame = frameObj as IVsWindowFrame;  
   if (frame == null)  
       <<do nothing>>;  
  
...  
   object pvar;  
   ErrorHandler.ThrowOnFailure(frame.GetProperty((int)__VSFPROPID.VSFPROPID_DocView,  
                                                  out pvar));  
  
   IVsTextView textView = pvar as IVsTextView;  
   if (textView == null)  
   {  
       IVsCodeWindow codeWin = pvar as IVsCodeWindow;  
       if (codeWin != null)  
       {  
           ErrorHandler.ThrowOnFailure(codeWin.GetLastActiveView(out textView));  
       }  
   }  
  
...  
   if (textView == null)  
       <<do nothing>>  
  
   IVsUserData userData = textView as IVsUserData;  
   if (userData == null)  
       <<do nothing>>  
  
   object objTextViewHost;  
   if (VSConstants.S_OK   
           != userData.GetData(Microsoft.VisualStudio.Editor.DefGuidList  
                                                            .guidIWpfTextViewHost,  
                                out objTextViewHost))  
   {  
       <<do nothing>>  
   }  
  
   IWpfTextViewHost textViewHost = objTextViewHost as IWpfTextViewHost;  
   if (textViewHost == null)  
       <<do nothing>>  
  
   IWpfTextView textView = textViewHost.TextView;  
  
```  
  
 IWpfTextView를 만든 후에 캐럿이 있는 열을 얻을 수 있습니다.  
  
```csharp  
private static int GetCaretColumn(IWpfTextView textView)  
{  
    // This is the code the editor uses to populate the status bar.  
    Microsoft.VisualStudio.Text.Formatting.ITextViewLine caretViewLine =  
        textView.Caret.ContainingTextViewLine;  
    double columnWidth = textView.FormattedLineSource.ColumnWidth;  
    return (int)(Math.Round((textView.Caret.Left - caretViewLine.Left)  
                                / columnWidth));  
}  
  
```  
  
 현재 열과 함께 사용자가 클릭 한 경우 코드 방금에 호출의 설정 관리자를 추가 하거나 열을 제거 합니다.  설정 관리자에 모든 이벤트를 발생 시킵니다. `ColumnGuideAdornment` 개체 수신 대기 합니다.  이벤트가 발생할 때 이러한 개체의 연결 된 텍스트 뷰 새 열 가이드 설정으로 업데이트 합니다.  
  
## <a name="invoking-command-from-the-command-window"></a>명령 창에서 호출 명령  
 열 안내선 샘플을 사용 하면 확장성 형태로 명령 창에서 두 명령을 호출할 수 있습니다.  사용 하는 경우는 **보기 &#124; 다른 창 &#124; 명령 창** 명령, 명령 창이 나타날 수 있습니다.  "편집"을 입력 하 여 명령 창 상호 작용할 수 있습니다 및 다음 항목이 명령 이름 완성 및 120 인수를 제공 합니다.  
  
```  
> Edit.AddColumnGuide 120  
>  
```  
  
 .Vsct 파일 선언에이는 사용할 수 있는 샘플의 조각을 `ColumnGuideCommands` 명령 처리기와 이벤트 인수를 확인 하는 명령 처리기 구현을 후크 하는 경우 클래스 생성자입니다.  
  
 언급 했 듯이 "`<CommandFlag>CommandWellOnly</CommandFlag>`" 편집 주 메뉴의 배치를.vsct 파일에도 म 표시 안 함 명령에는 **편집** 메뉴 UI입니다.  와 같은 이름을 제공 주 편집 메뉴에 있는 것 **Edit.AddColumnGuide**합니다.  명령을 그룹 4 개 명령은 편집 메뉴에서 직접 그룹을 배치를 보유 하는 선언:  
  
```xml  
<Group guid="guidColumnGuidesCommandSet" id="GuidesMenuItemsGroup"  
             priority="0xB801">  
        <Parent guid="guidSHLMainMenu" id="IDM_VS_MENU_EDIT" />  
      </Group>  
  
```  
  
 단추 섹션에는 나중에 명령을 선언 `CommandWellOnly` 으로 유지 하기 위해 보이지 않는 주 메뉴를 사용 하 여 선언 `AllowParams`:  
  
```xml  
<Button guid="guidColumnGuidesCommandSet" id="cmdidAddColumnGuide"   
        priority="0x0100" type="Button">  
  <Parent guid="guidColumnGuidesCommandSet" id="GuidesMenuItemsGroup" />  
  <Icon guid="guidImages" id="bmpPicAddGuide" />  
  <CommandFlag>CommandWellOnly</CommandFlag>  
  <CommandFlag>AllowParams</CommandFlag>  
  
```  
  
 명령 처리기 코드에 연결 했 듯이 `ColumnGuideCommands` 클래스 생성자 매개 변수의 허용된에 대 한 설명을 제공 합니다.  
  
```csharp  
_addGuidelineCommand.ParametersDescription = "<column>";  
  
```  
  
 언급 했 듯이 `GetApplicableColumn` 검사 함수 `OleMenuCmdEventArgs` 현재 열에 대 한 편집기의 보기를 확인 하기 전에 값에 대 한 합니다.  
  
```csharp  
private int GetApplicableColumn(EventArgs e)  
{  
    var inValue = ((OleMenuCmdEventArgs)e).InValue as string;  
    if (!string.IsNullOrEmpty(inValue))  
    {  
        int column;  
        if (!int.TryParse(inValue, out column) || column < 0)  
            throw new ArgumentException("Invalid column");  
        return column;  
    }  
  
```  
  
## <a name="trying-your-extension"></a>확장 프로그램을 시도  
 이제 누르면 **F5** 열 안내선 확장 프로그램을 실행 합니다.  텍스트 파일을 열고 안내선을 추가, 제거 및 해당 색을 변경 하려면 편집기의 상황에 맞는 메뉴를 사용 합니다.  텍스트의 클릭 해야 (공백 문자는 줄의 끝을 통과 하는 데 사용) 열을 추가 하려면 안내선 또는 편집기에 추가 된 줄에서 마지막 열입니다.  명령 창을 사용 하 고 인수를 사용 하 여 명령을 호출 하는 경우 열 안내선 임의의 위치를 추가할 수 있습니다.  
  
 다른 명령 배치를 시도, 이름 변경, 아이콘 및 등을 변경 하 고 메뉴에 최신 코드를 표시 하는 Visual Studio와 함께 문제가 있는 경우에 디버깅 하는 실험 하이브를 재설정할 수 있습니다.  표시는 **Windows 시작 메뉴** "초기화"를 입력 합니다.  검색 하 고 명령을 호출 **다음 Visual Studio 실험적 인스턴스 다시 설정**합니다.  이 모든 확장 구성 요소의 실험 레지스트리 하이브에서를 정리합니다.  그렇지 않으면 구성 요소에서 설정 아웃 정리 하므로 Visual Studio의 실험 하이브에서를 종료할 때 사용 했던 모든 안내선 계속 됩니다 있습니다 코드 다음 시작 시 설정 저장소를 읽을 때 서비스입니다.  
  
## <a name="finished-code-project"></a>완성 된 코드 프로젝트  
 Visual Studio 확장성 샘플 github 프로젝트가 됩니다 곧 하 고 완료 된 프로젝트 발생 됩니다.  이 항목에 도달 하면 지점을 업데이트 됩니다.  완성 된 샘플 프로젝트에는 다른 guid 없고 명령 아이콘에 대 한 다른 비트맵 스트립을 갖습니다.  
  
 이 Visual Studio 갤러리와 열 안내선 기능의 버전을 수행 하려면[확장](https://visualstudiogallery.msdn.microsoft.com/da227a0b-0e31-4a11-8f6b-3a149cf2e459?SRC=Home)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [편집기 내부에서](../extensibility/inside-the-editor.md)   
 [편집기 및 언어 서비스 확장](../extensibility/extending-the-editor-and-language-services.md)   
 [언어 서비스 및 편집기 확장 지점](../extensibility/language-service-and-editor-extension-points.md)   
 [확장 메뉴 및 명령](../extensibility/extending-menus-and-commands.md)   
 [메뉴에는 하위 메뉴 추가](../extensibility/adding-a-submenu-to-a-menu.md)   
 [편집기 항목 템플릿을 사용하여 확장 만들기](../extensibility/creating-an-extension-with-an-editor-item-template.md)
