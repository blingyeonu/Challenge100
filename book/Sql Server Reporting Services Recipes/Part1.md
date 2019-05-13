SSRS report Properties 코드부분에 넣을 때 에러가 발생


#### GreenBarReports
원래 코드

```
Private bOddRow As Boolean

Function AlternateColor (ByVal OddColor As String, ByVal EvenColor As String, ByVal Toggle As Boolean) As String
	IF Toggle Then bOddRow = Not bOddRow
		IF bOddRow Then
			Return OddColor
		Else 
			Return EvenColor
		End If
	End If
End Function
```

변경된 코드

```
Private bOddRow As Boolean

Function AlternateColor (ByVal OddColor As String, ByVal EvenColor As String, ByVal Toggle As Boolean) As String
	IF (Toggle = True) Then 
                    bOddRow = Not bOddRow
		IF (bOddRow = True) Then
			Return OddColor
		Else 
			Return EvenColor
		End If
	End If
End Function
```

변경된 코드로 하니 에러가 안남.
코드에 문제가 있었으나 그걸 못찾았음.

에러가 안나도록 만들어서 코드에 문제가 있었는지 확인해볼 필용가 있었음.

#### Nested Group Green Bar Effect

Report Properties에 넣은 코드

```
Public Function IncrementVariable(var As Microsoft.ReportingServices.ReportProcessing.OnDemandReportObjectModel.Variable) As Double 
   var.Value = var.Value + 1
   return var.Value
End Function
```

Report Properties에서 Variable 옵션부분에 Read-Only  체크해제 반드시필요!

#### DynamicGroups

* Matrix로 설정
* 두 개의 Row group(Parent, Child), 한 개의 Column group
* Parameter 3개 추가 Parent, child, Column
* Parent에 Parent, Child 추가
* Column에 원하는 항목 추가
* Child에 = IIF(Parameters!ParentRowGroupParam.Value="Parent","Child", Nothing) / Another 추가
* Group Property에서 Group On Expression에서 각각 = Fields(Parameters!ParentRowGroupParam.Value).Value 와 같은 형식으로 변경
