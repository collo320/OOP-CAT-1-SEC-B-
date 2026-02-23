Private Sub btnCalculate_Click(sender As Object, e As EventArgs) Handles btnCalculate.Click
    Dim num1, num2, sum, difference, product As Integer

    Try
        ' Check for empty input
        If String.IsNullOrWhiteSpace(txtNum1.Text) Or String.IsNullOrWhiteSpace(txtNum2.Text) Then
            Throw New Exception("Input cannot be empty. Please enter valid numbers.")
        End If

        ' Convert input to integers
        num1 = CInt(txtNum1.Text)
        num2 = CInt(txtNum2.Text)

        ' Compute values
        sum = num1 + num2
        difference = num1 - num2
        product = num1 * num2

        ' Display results
        lblResult.Text = $"Sum = {sum}{Environment.NewLine}Difference = {difference}{Environment.NewLine}Product = {product}"

    Catch ex As FormatException
        ' Handle non-numeric input
        MessageBox.Show("Input is not numeric. Please enter valid integers.", "Error", MessageBoxButtons.OK, MessageBoxIcon.Error)
    Catch ex As Exception
        ' Handle other errors (including empty input)
        MessageBox.Show(ex.Message, "Error", MessageBoxButtons.OK, MessageBoxIcon.Error)
    Finally
        ' Clear text boxes (optional but recommended)
        txtNum1.Clear()
        txtNum2.Clear()
    End Try
End Sub