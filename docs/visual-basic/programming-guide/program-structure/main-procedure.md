---
title: Visual Basic의 Main 프로시저
ms.date: 07/20/2015
f1_keywords:
- vb.Main
helpviewer_keywords:
- Main procedure
- Main method [Visual Basic]
- main function
ms.assetid: f0db283e-f283-4464-b521-b90858cc1b44
ms.openlocfilehash: 109bf94eb91292cfca700a9e456c8ab53e83d68f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33652154"
---
# <a name="main-procedure-in-visual-basic"></a>Visual Basic의 Main 프로시저
모든 Visual Basic 응용 프로그램은 `Main`이라는 프로시저를 포함해야 합니다. 이 프로시저는 응용 프로그램의 시작점이며 전체적인 제어로서 역할을 합니다. .NET Framework는 응용프로그램을 로드할 때 `Main` 프로시저를 호출하여 제어를 전달하도록 준비합니다. Windows Forms 응용 프로그램을 만들 경우를 제외하고는,  응용 프로그램을 실행시킬 `Main`프로시저를 작성해야 합니다. 
  
 `Main`은 처음으로 실행되는 코드를 포함합니다. `Main`에서, 프로그램이 시작할 때 어떤 폼을 처음으로 로드할 지를 결정하거나, 응용 프로그램의 복사본이 시스템에서 이미 실행되고 있는지를 확인하거나, 응용 프로그램에 대한 일련의 변수를 설정하거나, 응용 프로그램에 필요한 데이터베이스를 열 수 있습니다.  
  
## <a name="requirements-for-the-main-procedure"></a>Main 프로시저에 대한 요구 사항  
 자체적으로 실행되는 파일(일반적으로 확장명이.exe)은 `Main`프로시저를 포함해야 합니다. 라이브러리(예를 들어 확장명.dll)는 자체적으로 실행되지 않으며, `Main` 프로시저가 필요하지 않습니다. 만들 수 있는 다양한 유형의 프로젝트에 대한 요구 사항은 다음과 같습니다.  
  
-   콘솔 응용 프로그램은 자체적으로 실행되며, 하나 이상 `Main` 프로시저를 제공해야 합니다.  
  
-   Windows Forms 응용 프로그램은 자체적으로 실행됩니다. 그러나 Visual Basic 컴파일러가 자동으로 `Main`를 생성하여, 사용자가 작성할 필요는 없습니다.  
  
-   클래스 라이브러리는 `Main` 프로시저가 필요하지 않습니다. 여기에는 Windows 컨트롤 라이브러리와 웹 컨트롤 라이브러리도 포함됩니다. 웹 응용 프로그램은 클래스 라이브러리로 배포됩니다.  
  
## <a name="declaring-the-main-procedure"></a>Main 프로시저 선언하기  
 4 가지 방법으로 선언 하는 `Main` 프로시저입니다. 또는, 인수를 사용할 수 및 여부 값을 반환할 수 있습니다.  
  
> [!NOTE]
>  클래스 안에서 `Main`을 선언하는 경우에는 반드시 `Shared` 키워드를 사용해야 합니다. 모듈 안에서는 `Main`에 `Shared`가 필요하지 않습니다.  
  
-   가장 간단하게 선언하는 방법은, 인수도 받지 않고 값도 반환하지 않는 `Sub` 프로시저를 선언하는 것입니다.  
  
    ```  
    Module mainModule  
        Sub Main()  
            MsgBox("The Main procedure is starting the application.")  
            ' Insert call to appropriate starting place in your code.  
            MsgBox("The application is terminating.")  
        End Sub  
    End Module  
    ```  
  
-   `Main`은 `Integer`값을 반환할 수도 있으며, 이 값은 프로그램에 대한 종료 코드로 운영 체제가 사용하는 값입니다. 다른 프로그램이 Windows ERRORLEVEL 값을 검사하여 이 코드를 테스트할 수 있습니다. 종료 코드를 반환하려면, `Main`을 `Sub` 프로시저 대신 `Function` 프로시저로 선언해야 합니다.  
  
    ```  
    Module mainModule  
        Function Main() As Integer  
            MsgBox("The Main procedure is starting the application.")  
            Dim returnValue As Integer = 0  
            ' Insert call to appropriate starting place in your code.  
            ' On return, assign appropriate value to returnValue.  
            ' 0 usually means successful completion.  
            MsgBox("The application is terminating with error level " &  
                 CStr(returnValue) & ".")  
            Return returnValue  
        End Function  
    End Module  
    ```  
  
-   `Main`은 `String`배열을 인수로 받을 수 있습니다. 배열의 각 문자열은, 프로그램을 호출하는 데 사용되는 명령줄 인수 중 하나를 포함하기도 합니다. 그 값에 따라 다른 작업을 수행할 수 있습니다.  
  
    ```  
    Module mainModule  
        Function Main(ByVal cmdArgs() As String) As Integer  
            MsgBox("The Main procedure is starting the application.")  
            Dim returnValue As Integer = 0  
            ' See if there are any arguments.  
            If cmdArgs.Length > 0 Then  
                For argNum As Integer = 0 To UBound(cmdArgs, 1)  
                    ' Insert code to examine cmdArgs(argNum) and take  
                    ' appropriate action based on its value.  
                Next argNum  
            End If  
            ' Insert call to appropriate starting place in your code.  
            ' On return, assign appropriate value to returnValue.  
            ' 0 usually means successful completion.  
            MsgBox("The application is terminating with error level " &  
                 CStr(returnValue) & ".")  
            Return returnValue  
        End Function  
    End Module  
    ```  
  
-   명령줄 인수를 확인만 하고, 종료 코드를  반환하지 않는 `Main`를 다음과 같이 선언할 수도 있습니다.  
  
    ```  
    Module mainModule  
        Sub Main(ByVal cmdArgs() As String)  
            MsgBox("The Main procedure is starting the application.")  
            Dim returnValue As Integer = 0  
            ' See if there are any arguments.  
            If cmdArgs.Length > 0 Then  
                For argNum As Integer = 0 To UBound(cmdArgs, 1)  
                    ' Insert code to examine cmdArgs(argNum) and take  
                    ' appropriate action based on its value.  
                Next argNum  
            End If  
            ' Insert call to appropriate starting place in your code.  
            MsgBox("The application is terminating.")  
        End Sub  
    End Module  
    ```  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>  
 <xref:System.Array.Length%2A>  
 <xref:Microsoft.VisualBasic.Information.UBound%2A>  
 [Visual Basic 프로그램의 구조](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)  
 [/main](../../../visual-basic/reference/command-line-compiler/main.md)  
 [공유](../../../visual-basic/language-reference/modifiers/shared.md)  
 [Sub 문](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [Function 문](../../../visual-basic/language-reference/statements/function-statement.md)  
 [Integer 데이터 형식](../../../visual-basic/language-reference/data-types/integer-data-type.md)  
 [String 데이터 형식](../../../visual-basic/language-reference/data-types/string-data-type.md)
