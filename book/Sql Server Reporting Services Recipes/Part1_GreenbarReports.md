SSRS report Properties 코드부분에 넣을 때 에러가 발생

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
