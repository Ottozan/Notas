<Window x:Class="Calculator.MainWindow"
        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        xmlns:local="clr-namespace:Calculator"
        mc:Ignorable="d"
        Title="Calculadora" Height="525" Width="350">

```xaml
<Grid Margin="10">
    <Grid.ColumnDefinitions>
        <ColumnDefinition Width="*"/>
        <ColumnDefinition Width="*"/>
        <ColumnDefinition Width="*"/>
        <ColumnDefinition Width="*"/>
    </Grid.ColumnDefinitions>
    <Grid.RowDefinitions>
        <RowDefinition Height="2*"/>
        <RowDefinition Height="*"/>
        <RowDefinition Height="*"/>
        <RowDefinition Height="*"/>
        <RowDefinition Height="*"/>
        <RowDefinition Height="*"/>
    </Grid.RowDefinitions>
    <Label x:Name="resultLabel"
           Content="0"
           HorizontalAlignment="Right"
           VerticalAlignment="Bottom"
           Grid.ColumnSpan="4"/>
    <Button x:Name="acButton"
            Style="{StaticResource additionalButtonStyle}"
            Content="AC"
            Grid.Row="1"/>
    <Button x:Name="negativeButton" 
            Style="{StaticResource additionalButtonStyle}"
            Content="+/-"
            Grid.Row="1"
            Grid.Column="1"/>
    <Button x:Name="percentageButton" 
            Style="{StaticResource additionalButtonStyle}"
            Content="%"
            Grid.Row="1"
            Grid.Column="2"/>
    <Button x:Name="divideButton" Content="/"
            Click="OperationButton_Click"
            Style="{StaticResource operatorButtonStyle}"
            Grid.Row="1"
            Grid.Column="3"/>
    <Button x:Name="sevenButton" 
            Click="numberButton_Click"
            Style="{StaticResource numberButtonStyle}"
            Content="7"
            Grid.Row="2"/>
    <Button Content="8" x:Name="eightButton" 
            Click="numberButton_Click"
            Style="{StaticResource numberButtonStyle}"
            Grid.Row="2"
            Grid.Column="1"/>
    <Button Content="9" x:Name="nineButton" 
            Style="{StaticResource numberButtonStyle}"
            Click="numberButton_Click"
            Grid.Row="2"
            Grid.Column="2"/>
    <Button Content="*" x:Name="multiplyButton"
            Click="OperationButton_Click"
            Style="{StaticResource operatorButtonStyle}"
            Grid.Row="2"
            Grid.Column="3"/>
    <Button Content="4" x:Name="fourButton"
            Style="{StaticResource numberButtonStyle}" 
            Click="numberButton_Click"
            Grid.Row="3"/>
    <Button Content="5" x:Name="fiveButton"
            Style="{StaticResource numberButtonStyle}" 
            Click="numberButton_Click"
            Grid.Row="3"
            Grid.Column="1"/>
    <Button Content="6" x:Name="sixButton" 
            Style="{StaticResource numberButtonStyle}"
            Click="numberButton_Click"
            Grid.Row="3"
            Grid.Column="2"/>
    <Button Content="-" x:Name="minusButton"
            Click="OperationButton_Click"
            Style="{StaticResource operatorButtonStyle}"
            Grid.Row="3"
            Grid.Column="3"/>
    <Button Content="1" x:Name="oneButton" 
            Style="{StaticResource numberButtonStyle}"
            Click="numberButton_Click"
            Grid.Row="4"/>
    <Button Content="2" x:Name="twoButton" 
            Style="{StaticResource numberButtonStyle}"
            Click="numberButton_Click"
            Grid.Row="4"
            Grid.Column="1"/>
    <Button Content="3" x:Name="threeButton"
            Click="numberButton_Click"
            Style="{StaticResource numberButtonStyle}" 
            Grid.Row="4"
            Grid.Column="2"/>
    <Button Content="+" x:Name="plusButton"
            Click="OperationButton_Click"
            Style="{StaticResource operatorButtonStyle}"
            Grid.Row="4"
            Grid.Column="3"/>
    <Button Content="0" x:Name="zeroButton" 
            Click="numberButton_Click"
            Style="{StaticResource numberButtonStyle}"
            Grid.Row="5"
            Grid.ColumnSpan="2"/>
    <Button Content="." x:Name="dotButton"
            Click="dotButton_Click"
            Style="{StaticResource numberButtonStyle}"
            Grid.Row="5"
            Grid.Column="2"/>
    <Button Content="=" x:Name="equalsButton"
            Style="{StaticResource operatorButtonStyle}"
            Grid.Row="5"
            Grid.Column="3"/>
</Grid>
```
