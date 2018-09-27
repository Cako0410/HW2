

# HW2 Easy Solution
Sub StockA()

    For Each ws In Worksheets
        Dim Total_stock_volume As Double
        Total_stock_volume = 0
        Dim ticker As String
        Dim summary_table_row As Integer
        summary_table_row = 2
       
        last_row = ws.Cells(Rows.Count, 1).End(xlUp).Row
        
        ws.Range("I1").Value = "ticker"
        ws.Range("J1").Value = "total_stock_volume"

        For i = 2 To last_row
        
               If ws.Cells(i , 1).Value <> ws.Cells(i+1, 1).Value Then

                     ticker = ws.Cells(i, 1).Value
               
                    Total_stock_volume = Total_stock_volume + ws.Cells(i, 7).Value
               
                    ws.Range("I" & summary_table_row)= ticker
                    ws.Range("J" & summary_table_row)= Total_stock_volume
                    summary_table_row = summary_table_row + 1
                    Total_stock_volume = 0


             Else

                    Total_stock_volume = Total_stock_volume + ws.Cells(i, 7).Value

             End If


     Next i

  Next
  
End Sub









