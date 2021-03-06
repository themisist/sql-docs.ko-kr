---
title: Execute, Requery 및 Clear 메서드 예제 (VB) | Microsoft Docs
ms.prod: sql
ms.prod_service: connectivity
ms.technology: connectivity
ms.custom: ''
ms.date: 01/19/2017
ms.reviewer: ''
ms.topic: conceptual
dev_langs:
- VB
helpviewer_keywords:
- Requery method [ADO], Visual Basic example
- Clear method [ADO], Visual Basic example
- Execute method [ADO], Visual Basic example
ms.assetid: ed5e1b60-3769-4b26-a253-1d721e37941d
author: rothja
ms.author: jroth
ms.openlocfilehash: 0ac9a84c9b4780ad149d3c614b9e3c52494ace8b
ms.sourcegitcommit: 6037fb1f1a5ddd933017029eda5f5c281939100c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2020
ms.locfileid: "82760169"
---
# <a name="execute-requery-and-clear-methods-example-vb"></a>Execute, Requery 및 Clear 메서드 예제 (VB)
이 예제에서는 [명령](../../../ado/reference/ado-api/command-object-ado.md) 개체와 [연결](../../../ado/reference/ado-api/connection-object-ado.md) 개체 모두에서 실행 되는 경우 **Execute** 메서드를 보여 줍니다. 또한 [Requery](../../../ado/reference/ado-api/requery-method.md) 메서드를 사용 하 여 [레코드 집합](../../../ado/reference/ado-api/recordset-object-ado.md)의 현재 데이터를 검색 하 고 [clear](../../../ado/reference/ado-api/clear-method-ado.md) 메서드를 사용 하 여 [Errors](../../../ado/reference/ado-api/errors-collection-ado.md) 컬렉션의 내용을 지웁니다. ( **Errors** 컬렉션은 [레코드 집합](../../../ado/reference/ado-api/recordset-object-ado.md)의 [ActiveConnection](../../../ado/reference/ado-api/activeconnection-property-ado.md) 속성의 **Connection** 개체를 통해 액세스 됩니다.) 이 프로시저를 실행 하려면 ExecuteCommand 및 PrintOutput 프로시저가 필요 합니다.  
  
```  
'BeginExecuteVB  
  
    'To integrate this code  
    'replace the data source and initial catalog values  
    'in the connection string  
  
Public Sub Main()  
    On Error GoTo Err_Execute  
  
    ' connection, command, and recordset variables  
    Dim Cnxn As ADODB.Connection  
    Dim cmdChange As ADODB.Command  
    Dim rstTitles As ADODB.Recordset  
    Dim Err As ADODB.Error  
    Dim strSQLChange As String  
    Dim strSQLRestore As String  
    Dim strSQLTitles  
    Dim strCnxn As String  
  
     ' Define two SQL statements to execute as command text  
    strSQLChange = "UPDATE Titles SET Type = 'self_help' WHERE Type = 'psychology'"  
    strSQLRestore = "UPDATE Titles SET Type = 'psychology' WHERE Type = 'self_help'"  
  
     ' Open connection  
    strCnxn = "Provider='sqloledb';Data Source='MySqlServer';" & _  
        "Initial Catalog='Pubs';Integrated Security='SSPI';"  
    Set Cnxn = New ADODB.Connection  
    Cnxn.Open strCnxn  
  
     ' Create command object  
    Set cmdChange = New ADODB.Command  
    Set cmdChange.ActiveConnection = Cnxn  
    cmdChange.CommandText = strSQLChange  
  
     ' Open titles table  
    Set rstTitles = New ADODB.Recordset  
    strSQLTitles = "titles"  
    rstTitles.Open strSQLTitles, Cnxn, , , adCmdTable  
  
    ' Print report of original data  
    Debug.Print _  
       "Data in Titles table before executing the query"  
    PrintOutput rstTitles  
  
    ' Call the ExecuteCommand subroutine below to execute cmdChange command  
    ExecuteCommand cmdChange, rstTitles  
  
    ' Print report of new data  
    Debug.Print _  
       "Data in Titles table after executing the query"  
    PrintOutput rstTitles  
  
    ' Use the Connection object's execute method to  
    ' execute SQL statement to restore data and trap for  
    ' errors, checking the Errors collection if necessary  
    Cnxn.Execute strSQLRestore, , adExecuteNoRecords  
  
    ' Retrieve the current data by requerying the recordset  
    rstTitles.Requery  
  
    ' Print report of restored data using sub from below  
    Debug.Print "Data after executing the query to restore the original information "  
    PrintOutput rstTitles  
  
    ' clean up  
    rstTitles.Close  
    Cnxn.Close  
    Set rstTitles = Nothing  
    Set Cnxn = Nothing  
    Exit Sub  
  
Err_Execute:  
    ' Notify user of any errors that result from  
    ' executing the query  
    If rstTitles.ActiveConnection.Errors.Count >= 0 Then  
       For Each Err In rstTitles.ActiveConnection.Errors  
          MsgBox "Error number: " & Err.Number & vbCr & _  
             Err.Description  
       Next Err  
    End If  
  
    ' clean up  
    If Not rstTitles Is Nothing Then  
        If rstTitles.State = adStateOpen Then rstTitles.Close  
    End If  
    Set rstTitles = Nothing  
  
    If Not Cnxn Is Nothing Then  
        If Cnxn.State = adStateOpen Then Cnxn.Close  
    End If  
    Set Cnxn = Nothing  
  
    If Err <> 0 Then  
        MsgBox Err.Source & "-->" & Err.Description, , "Error"  
    End If  
End Sub  
  
Public Sub ExecuteCommand(cmdTemp As ADODB.Command, rstTemp As ADODB.Recordset)  
  
   Dim Err As Error  
  
   ' Run the specified Command object and trap for  
   ' errors, checking the Errors collection  
   On Error GoTo Err_Execute  
   cmdTemp.Execute  
   On Error GoTo 0  
  
   ' Retrieve the current data by requerying the recordset  
   rstTemp.Requery  
  
   Exit Sub  
  
Err_Execute:  
  
   ' Notify user of any errors that result from  
   ' executing the query  
   If rstTemp.ActiveConnection.Errors.Count > 0 Then  
      For Each Err In rstTemp.ActiveConnection.Errors  
         MsgBox "Error number: " & Err.Number & vbCr & _  
            Err.Description  
      Next Err  
   End If  
  
   Resume Next  
  
End Sub  
  
Public Sub PrintOutput(rstTemp As ADODB.Recordset)  
  
   ' Enumerate Recordset  
   Do While Not rstTemp.EOF  
      Debug.Print "  " & rstTemp!Title & _  
         ", " & rstTemp!Type  
      rstTemp.MoveNext  
   Loop  
  
End Sub  
'EndExecuteVB  
```  
  
## <a name="see-also"></a>참고 항목  
 [Clear 메서드 (ADO)](../../../ado/reference/ado-api/clear-method-ado.md)   
 [Command 개체 (ADO)](../../../ado/reference/ado-api/command-object-ado.md)   
 [Connection 개체 (ADO)](../../../ado/reference/ado-api/connection-object-ado.md)   
 [Error 개체](../../../ado/reference/ado-api/error-object.md)   
 [Execute 메서드 (ADO 명령)](../../../ado/reference/ado-api/execute-method-ado-command.md)   
 [Execute 메서드 (ADO 연결)](../../../ado/reference/ado-api/execute-method-ado-connection.md)   
 [레코드 집합 개체 (ADO)](../../../ado/reference/ado-api/recordset-object-ado.md)   
 [Requery 메서드](../../../ado/reference/ado-api/requery-method.md)
