---
title: "ML Studio (classic): Apply Math Operation - Azure"
description: Learn how to use the Apply Math Operation module to create calculations that are applied to numeric columns in the input dataset.
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"
author: xiaoharper
ms.author: amlstudiodocs 
manager: cgronlun
---
# Apply Math Operation
*Applies a mathematical operation to column values*  
  
 Category: [Statistical Functions](statistical-functions.md)  

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]
  
## Module overview  

This article describes how to use the **Apply Math Operation** module in Machine Learning Studio (classic), to create calculations that are applied to numeric columns in the input dataset. 

Supported math operations include common arithmetic functions such as multiplication and division, trigonometric functions, a variety of rounding functions, and special functions used in data science such as gamma and error functions.  

After you define an operation and run the experiment, the values are added to your dataset. Depending on how you configure the module, you can:

+ Append the results to your dataset. This is particularly useful when you are verifying the result of the operation.
+ Replace columns values with the new, computed values.
+ Generate a new column for results, and not show the original data. 

> [!TIP]
> This module performs a single math operation at a time. For complex math operations, we recommend using these modules instead:
> 
> + [Execute R Script](execute-r-script.md)
> + [Execute Python Script](execute-python-script.md)
> + [Apply SQL Transformation](apply-sql-transformation.md)  

Look for the operation you need in these categories:  

- [Basic](#bkmk_Basic)  
  
     The functions in the **Basic** category can be used to manipulate a single value or column of values. For example, you might get the absolute value of all numbers in a column, or calculate the square root of each value in a column.  
  
-   [Compare](#bkmk_Compare)  
  
      The functions in the **Compare** category are all used for comparison: you can do a pair-wise comparison of the values in two columns, or you can compare each value in a column to a specified constant. For example, you could compare columns to determine whether values were the same in two datasets. Or, you might use a constant, such as a maximum allowed value, to find outliers in a numeric column.  
  
-   [Operations](#bkmk_Arithmetic)  
  
     This category includes the basic mathematical functions: addition, subtraction, multiplication, and division. You can work with either columns or constants. For example, you might add the value in Column A to the value in Column B. Or, you might subtract a constant, such as a previously calculated mean, from each value in Column A.  
  
-   [Rounding](#bkmk_Rounding)  
  
     This category includes a variety of functions for performing operations such as rounding, ceiling, floor, and truncation to various levels of precision. You can specify the level of precision for both decimal and whole numbers.  
  
-   [Special mathematical functions](#bkmk_Special)  
  
     The **Special** category includes mathematical functions that are especially used in data science, such as elliptic integrals and the Gaussian error function.  
  
-   [Trigonometric functions](#bkmk_Trig)  
  
     This category includes all standard trigonometric functions. For example, you can convert radians to degrees, or compute functions such as tangent in either radians or degrees.
     These functions are unary, meaning that they take a single column of values as input, apply the trigonometric function, and return a column of values as the result.  Therefore you need to make sure that the input column is the appropriate type and contains the right kind of values for the specified operation.   


## Examples

For examples of how to use **Apply Math Operation**, see these sample experiments in the [Azure AI Gallery](https://gallery.azure.ai/):  
  
- [Color quantization](https://go.microsoft.com/fwlink/?LinkId=525272): One set of column values is subtracted from another, and then the results are squared.  
  
- [Customer relationship prediction](https://go.microsoft.com/fwlink/?LinkId=525941): The constant 1 is added to all values in a column to distinguish between zeros and missing values.  

- [Flight delay prediction](https://go.microsoft.com/fwlink/?LinkId=525725): Demonstrates various operations, including rounding and division.  

- [Direct marketing](https://go.microsoft.com/fwlink/?LinkId=525168): Uses comparison operations to determine whether probability scores meet a required value.  

## How to use Apply Math Operation  

The **Apply Math Operation** module requires a dataset that contains at least one column containing only numbers. The numbers can be discrete or continuous but must be of a numeric data type, not a string.

You can apply the same operation to multiple numeric columns, but all columns must be in the same dataset. 

Each instance of this module can perform only one type of operation at a time. To perform complex math operations, you might need to chain together several instances of the **Apply Math Operation** module.  
  
1.  Add the **Apply Math Operation** module to your experiment. You can find this module in the [Statistical Functions](statistical-functions.md) category.

2. Connect a dataset that contains at least one numeric column.  
  
3.  Click **Category** to select the **type** of math operation to perform.

    For example, to do basic arithmetic on columns, choose **Operations**. To get a logarithm or a ceiling, choose **Basic**. To compare columns of values, use **Comparison**. 
    
    > [!TIP]
    > All other options change depending on what type of mathematical operation you choose. Also, any change to the category resets all other options. Therefore, be sure to select from **Category**  first!
    
4. Choose a specific operation from the list in that category.
  
4.  Select one or more source columns on which to perform the calculation.   
  
    + Any column that you choose must be a numeric data type. 
    + The range of data must be valid for the selected mathematical operation. Otherwise an error or NaN (not a number) result may occur. For example, Ln(-1.0) is an invalid operation and results in a value of `NaN`.
  
4.  Set additional parameters required by each type of operation.  
  
5.  Use the **Output mode** option to indicate how you want the math operation to be generated: 

    - **Append**. All the columns used as inputs are included in the output dataset, plus one additional column is appended that contains the results of the math operation.
    - **Inplace**. The values in the columns used as inputs are replaced with the new calculated values. 
    - **ResultOnly**. A single column is returned containing the results of the math operation.
  
6.  Run the experiment, or right-click just the **Apply Math Operation** module and select **Run selected**.  
  
### Results

If you generate the results using the **Append** or **ResultOnly** options, the column headings of the returned dataset indicate the operation and the columns that were used. For example, if you compare two columns using the **Equals** operator, the results would look like this:  
  
-   **Equals(Col2_Col1)**,  indicating that you tested Col2 against Col1.  
-   **Equals(Col2_$10)**, indicating that you compared column 2 to the constant 10.  

Even if you use the **Inplace** option, the source data is not deleted or changed; the column in the original dataset is still available in Studio (classic). To view the original data, you can connect the [Add Columns](add-columns.md) module and join it to the output of **Apply Math Operation**.  
    
## <a name="bkmk_Basic"></a> Basic math operations 

The functions in the **Basic** category usually take a single value from a column, perform the predefined operation, and return a single value. For some functions you can specify a constant as a second argument.  
  
 Machine Learning supports the following functions in the **Basic** category:  

### Abs

Returns the absolute value of the selected columns.  
  
### Atan2

Returns a four-quadrant inverse tangent.  

Select the columns that contain the point coordinates. For the second argument, which corresponds to the x-coordinate, you can also specify a constant.  

Corresponds to the ATAN2 function in Matlab.  

### Conj

Returns the conjugate for the values in the selected column.  

### CubeRoot

Calculates the cube root for the values in the selected column.  

### DoubleFactorial**  
 Calculates the double factorial for values in the selected column. The double factorial is an extension of the normal factorial function, and it is denoted as x!!.  

### Eps

Returns the size of the gap between the current value and the next-highest, double-precision number. Corresponds to the EPS function in Matlab.  
  
### Exp

Returns e raised to the power of the value in the selected column. This is the same as the Excel EXP function.  

### Exp2

Returns the base-2 exponential of the arguments, solving for y = x * 2<sup>t</sup> where t is a column of values containing exponents.  

For **Exp2** you can specify a second argument x, which can be either a constant or another column of values  

In **Second argument type**, indicate whether you will provide the multiplier t as a constant, or a value in a column.  

You can select a single column with the exponent values, or type the exponent value in the **Constant second argument** text box. Then, in  **Column set**, select the column that contains the exponent values.  

For example, if you select a column with the values {0,1,2,3,4,5} for both the multiplier and the exponent, the function returns {0, 2, 8, 24, 64 160).  

### ExpMinus1 

Returns the negative exponent for values in the selected column.  

### Factorial
Returns the factorial for values in the selected column.  

### Hypotenuse
Calculates the hypotenuse for a triangle in which the length of one side is specified as a column of values, and the length of the second side is specified either as a constant or as two columns.  

### ImaginaryPart

Returns the imaginary part of the values in the selected column.  

### Ln

Returns the natural logarithm for the values in the selected column.  

### LnPlus1

Returns the natural logarithm plus one for the values in the selected column.  

### Log

Returns the log of the values in the selected column, given the specified base.  

You can specify the base (the second argument) either as a constant or by selecting another column of values.  

### Log10

Returns the base 10 logarithm the values in the selected column.  

### Log2

Returns the base 2 logarithm for the values in the selected column.  

### NthRoot
Returns the nth root of the value, using an n that you specify.  

Select the columns for which you want to calculate the root, by using the **ColumnSet** option.  

In **Second argument type**, select another column that contains the root, or specify a constant to use as the root.  

If the second argument is a column, each value in the column is used as the value of n for the corresponding row. If the second argument is a constant, type the value for n in the **Constant second argument** text box.
### Pow

Calculates X raised to the power of Y for each of the values in the selected column.  

First, select the columns that contains the **base**, which should be a float, by using the **ColumnSet** option.  

In **Second argument type**, select the column that contains the exponent, or specify a constant to use as the exponent.  

If the second argument is a column, each value in the column is used as the exponent for the corresponding row. If the second argument is a constant, type the value for the exponent in the **Constant second argument** text box.  

### RealPart

Returns the real part of the values in the selected column.  

### Sqrt

Returns the square root of the values in the selected column.  

### SqrtPi

For each value in the selected column, multiplies the value by pi and then returns the square root of the result.  

### Square

Squares the values in the selected column.  

## <a name="bkmk_Compare"></a> Comparison operations  

Use the comparison functions in Machine Learning Studio (classic) any time that you need to test two sets of values against each other. For example, in an experiment you might need to do these comparison operations:  

- Evaluate a column of probability scores model against a threshold value.
- Determine if two sets of results are the same, and for each row that is different, add a FALSE flag that can be used for further processing or filtering.  

### EqualTo

Returns True if the values are the same.  

### GreaterThan

Returns True if the values in **Column set** are greater than the specified constant, or greater than the corresponding values in the comparison column.  

### GreaterThanOrEqualTo

Returns True if the values in **Column set** are greater than or equal to the specified constant, or greater than or equal to the corresponding values in the comparison column.  

### LessThan

Returns True if the values in **Column set** are less than the specified constant, or less than the corresponding values in the comparison column.  
  
### LessThanOrEqualTo

Returns True if the values in **Column set** are less than or equal to the specified constant, or less than or equal to the corresponding values in the comparison column.  

### NotEqualTo

Returns True if the values in **Column set** are not equal to the constant or comparison column, and returns False if they are equal.  

### PairMax

Returns the value that is greater—the value in **Column set** or the value in the constant or comparison column.  

### PairMin

Returns the value that is lesser—the value in **Column set** or the value in the constant or comparison column  
  
##  <a name="bkmk_Arithmetic"></a> Arithmetic operations   

Includes the basic arithmetic operations: addition and subtraction, division and multiplication.  Because most operations are binary, requiring two numbers, you first choose the operation, and then choose the column or numbers to use in the first and second arguments.

The order in which you choose the columns for division and subtraction might seem counterintuitive; however, to make it easier to understand the results, the column heading provides the operation name, and the order in which the columns were used.

Operation|Num1|Num2|Result column|Result value|
----|----|----|----|----
|Addition|1|5|Add(Num2_Num1)| 4|
|Multiplication|1|5|Multiple(Num2_Num1)|5|
|Subtraction|1|5|Subtract(Num2_Num1)|4|
|Subtraction|0|1|Subtract(Num2_Num1)|0|
|Division|1|5|Divide(Num2_Num1)|5|
|Division|0|1|Divide(Num2_Num1)|Infinity|

### Add

Specify the source columns by using **Column set**, and then add to those values a number specified in **Constant operation argument**.  

To add the values in two columns, choose a column or columns using **Column set**, and then choose a second column using **Operation argument**.  

### Divide

Divides the values in **Column set** by a constant or by the column values defined in **Operation argument**.  In other words, you pick the divisor first, and then the dividend. The output value is the quotient.

### Multiply

Multiplies the values in **Column set** by the specified constant or column values.  

### Subtract

Specify the number to subtract (the *subtrahend*) by using the **Operation argument** dropdown list. You can choose either a constant or column of values. Then, specify the column of values to operate on (the *minuend*), by choosing a different column, using the second **Column set** option.  

You can subtract a constant from each value in a column of values, but not the reverse operation. To do this, use addition instead. 

##  <a name="bkmk_Rounding"></a> Rounding operations 

Studio (classic) supports a variety of rounding operations. For many operations, you must specify the amount of  precision to use when rounding. You can use either a static precision level, specified as a constant, or you can apply a dynamic precision value obtained from a column of values.  

+ If you use a constant, set **Precision Type** to **Constant** and then type the number of digits as an integer in the **Constant Precision** text box. If you type a non-integer, the module does not raise an error, but results can be unexpected.  

+ To use a different precision value for each row in your dataset, set **Precision Type** to **ColumnSet**, and then choose the column that contains appropriate precision values.  

### Ceiling

Returns the ceiling for the values in **Column set**.  

### CeilingPower2

Returns the squared ceiling for the values in **Column set**.  

### Floor

Returns the floor for the values in **Column set**, to the specified precision.  

### Mod

Returns the fractional part of the values in **Column set**, to the specified precision.  

### Quotient

Returns the fractional part of the values in **Column set**, to the specified precision.  

### Remainder

Returns the remainder for the values in **Column set**.  

### RoundDigits

Returns the values in **Column set**, rounded by the 4/5 rule to the specified number of digits.  

### RoundDown

Returns the values in **Column set**, rounded down to the specified number of digits.  

### RoundUp

Returns the values in **Column set**, rounded up to the specified number of digits.  

### ToEven

Returns the values in **Column set**, rounded to the nearest whole, even number.  

### ToOdd

Returns the values in **Column set**, rounded to the nearest whole, odd number.  

### Truncate

Truncates the values in **Column set** by removing all digits not allowed by the specified precision.  
  
##  <a name="bkmk_Special"></a> Special math functions

This category includes specialized mathematical functions often used in data science. Unless otherwise noted, the function is unary and returns the specified calculation for each value in the selected column or columns.  

### Beta

Returns the value of Euler’s beta function.  

### EllipticIntegralE
Returns the value of the incomplete elliptic integral.  
  

### EllipticIntegralK

Returns the value of the complete elliptic integral (K).  

### Erf

Returns the value of the error function.  

The error function (also called the Gauss error function) is a special function of the sigmoid shape that is used in probability to describe diffusion.  

### Erfc

Returns the value of the complementary error function.  

Erfc is defined as 1 – erf(x).  

### ErfScaled

Returns the value of the scaled error function.  

The scaled version of the error function can be used to avoid arithmetic underflow.  

### ErfInverse

Returns the value of the inverse erf function.  

### ExponentialIntegralEin

Returns the value of the exponential integral Ei.  

### Gamma

Returns the value of the gamma function.  

### GammaLn

Returns the natural logarithm of the gamma function.  

### GammaRegularizedP

Returns the value of the regularized incomplete gamma function.  

This function takes a second argument, which can be provided either as a constant or a column of values.  

### GammaRegularizedPInverse

Returns the value of the inverse regularized incomplete gamma function.  

This function takes a second argument, which can be provided either as a constant or a column of values.  

### GammaRegularizedQ  

Returns the value of the regularized incomplete gamma function.  

This function takes a second argument, which can be provided either as a constant or a column of values.  

### GammaRegularizedQInverse

Returns the value of the inverse generalized regularized incomplete gamma function.

This function takes a second argument, which can be provided either as a constant or a column of values.  

### PolyGamma

Returns the value of the polygamma function.  

This function takes a second argument, which can be provided either as a constant or a column of values.

##  <a name="bkmk_Trig"></a> Trigonometric functions 

This category iIncludes most of the important trigonometric and inverse trigonometric functions. All trigonometric functions are unary and require no additional arguments.  

### Acos

Calculates the arccosine for the column values.  

### AcosDegree

Calculates the arccosine of the column values, in degrees.  

### Acosh

Calculates the hyperbolic arccosine of the column values.  

### Acot

Calculates the arccotangent of the column values.  

### AcotDegrees

Calculates the arccotangent of the column values, in degrees.  

### Acoth

Calculates the hyperbolic arccotangent of the column values.  

### Acsc

Calculates the arccosecant of the column values.  

### AcscDegrees

Calculates the arccosecant of the column values, in degrees.  
### Asec

Calculates the arcsecant of the column values.  

### AsecDegrees

Calculates the arcsecant of the column values, in degrees.  

### Asech

Calculates the hyperbolic arcsecant of the column values.  

### Asin

Calculates the arcsine of the column values.  

### AsinDegrees

Calculates the arcsine of the column values, in degrees.  

### Asinh

Calculates the hyperbolic arcsine for the column values.  

### Atan

Calculates the arctangent of the column values.  

### AtanDegrees

Calculates the arctangent of the column values, in degrees.  

### Atanh

Calculates the hyperbolic arctangent of the column values.  

### Cis

Returns a complex-valued function made from sine and cosine with the definition cis θ = cos θ + isin θ.  

### Cos

Calculates the cosine of the column values.  

### CosDegrees

Calculates the cosine for the column values, in degrees.  

### Cosh

Calculates the hyperbolic cosine for the column values.  

### Cot

Calculates the cotangent for the column values.  

### CotDegrees

Calculates the cotangent for the column values, in degrees.  

### Coth
Calculates the hyperbolic cotangent for the column values.  

### Csc

Calculates the cosecant for the column values.  

### CscDegrees

Calculates the cosecant for the column values, in degrees.  

### Csch

Calculates the hyperbolic cosecant for the column values.  

### DegreesToRadians

Converts degrees to radians.  

### Sec

Calculates the secant of the column values.  

### aSecDegrees

Calculates the secant for the column values, in degrees.  

### aSech

Calculates the hyperbolic secant of the column values.  

### Sign

Returns the sign of the column values.  

### Sin

Calculates the sine of the column values.  

### Sinc

Calculates the sine-cosine value of the column values.  

### SinDegrees

Calculates the sine for the column values, in degrees.  

### Sinh

Calculates the hyperbolic sine of the column values.  

### Tan

Calculates the tangent of the column values.  

### TanDegrees

Calculates the tangent for the argument, in degrees.  

### Tanh

Calculates the hyperbolic tangent of the column values.  
  
## Technical notes

This section contains implementation details, tips, and answers to frequently asked questions.

### Operations on multiple columns

Be careful when you select more than one column as the second operator. The results are easy to understand if the operation is simple, such as adding a constant to all columns. 

Assume your dataset has multiple columns, and you add the dataset to itself. In the results, each column is added to itself, as follows:  
  
|Num1|Num2|Num3|Add(Num1_Num1)|Add(Num2_Num2)|Add(Num3_Num3)|
|----|----|----|----|----|----|
|1|5|2|2|10|4|
|2|3|-1|4|6|-2|
|0|1|-1|0|2|-2|

If you need to perform more complex calculations, you can chain multiple instances of **Apply Math Operation**. For example, you might add two columns by using one instance of **Apply Math Operation**, and then use another instance of **Apply Math Operation** to divide the sum by a constant to obtain the mean.  
  
Alternatively, use one of the following modules to do all the calculations at once, using SQL, R, or Python script :
 
+ [Execute R Script](execute-r-script.md)
+ [Execute Python Script](execute-python-script.md)
+ [Apply SQL Transformation](apply-sql-transformation.md)   

### Unary and binary functions  
  
In a *unary operation*, you create calculations based on column values without referring to other columns or constants.  
  
For example, you might truncate the column’s values to a certain degree of precision, round values up or down, or find ceiling or floor values.  
  
An example of a unary operation is `Abs(X)`, where X is the column that is provided as input.  
  
In a *binary operation*, you specify two sets of values. The first argument must always be a column or set of columns, while the second argument can be a number you specify as a constant, or another column.  
  
An example of a binary operation that uses two columns is `Subtract(X,Y)`, in which X is the first column you select, and Y is the second column.  
  
An example of using a binary operation that combines a column and a constant might be `Subtract(X,mean)`, where you type the column mean as a constant and subtract it from each value in column X.  
  
### Handling of numbers in categorical columns  
  
Support for categorical values presented as numbers depends on the function, and on how many arguments the function takes. 

+ If your operation includes numbers designated as categorical columns, a unary operation can be applied to categorical data values.  
  
+ If a unary operation is applied to a categorical column, the categorical data values of the input column can be transformed to equal associated categorical data values of the output column. In this case, the values are merged, such that the number of categorical data values in the output is always less than the number of values in the input.  
  
+ If a binary operation is applied to a categorical column and some other column, the expected behavior is as follows:  
  
    -   If the other column is dense, the output column is categorical.  
  
         Categorical data values presented in the input are lost.  
  
         The output column has only those values that are present in the output column data.  
  
    -   If the other column is sparse, the output column is sparse.  
  
    -   If both arguments of a binary operation are sparse columns, the resulting column contains background zeros in all positions where both input columns contained background zeros.  
  
### Processing of sparse columns

In unary operations, all elements of sparse columns that correspond to background zeros are left unprocessed.  
  
In binary operations, if one argument is a sparse column and the other argument is a dense column, the resulting column is sparse with all background zeros propagated from input from the sparse column.  
  
## Expected inputs  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Dataset|[Data Table](data-table.md)|Input dataset|  
  
## Outputs  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Results dataset|[Data Table](data-table.md)|Results dataset|  
  
## See also  

 [Statistical Functions](statistical-functions.md)   
 [A-Z Module List](a-z-module-list.md)
