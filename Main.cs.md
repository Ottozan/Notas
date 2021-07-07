using System.Windows;
using System.Windows.Controls;

namespace Calculator
{
    /// <summary>
    /// Interaction logic for MainWindow.xaml
    /// </summary>
    public partial class MainWindow : Window
    {
        double lastNumber, result;
        SelectedOperator selectedOperator;
        public MainWindow()
        {

            InitializeComponent();
            resultLabel.Content = "0";
            acButton.Click += AcButton_Click;
            negativeButton.Click += NegativeButton_Click;
            percentageButton.Click += PercentageButton_Click;
            equalsButton.Click += EqualsButton_Click;
    
        }
    
        private void EqualsButton_Click(object sender, RoutedEventArgs e)
        {
            double newNumber;
            if (double.TryParse(resultLabel.Content.ToString(), out newNumber))
            {
                switch (selectedOperator)
                {
                    case SelectedOperator.Addition:
                        result = SimpleMath.Add(lastNumber, newNumber);
                        break;
                    case SelectedOperator.Subtraction:
                        result = SimpleMath.Subtraction(lastNumber, newNumber);
                        break;
                    case SelectedOperator.Multiplication:
                        result = SimpleMath.Multiply(lastNumber, newNumber);
                        break;
                    case SelectedOperator.Division:
                        result = SimpleMath.Divide(lastNumber, newNumber);
                        break;
                    default:
                        result = 0;
                        break;
                }
    
                resultLabel.Content = result.ToString();
            }
    
        }
    
        //private void EightButton_Click(object sender, RoutedEventArgs e)
        //{
        //    if (double.TryParse(resultLabel.Content.ToString(), out lastNumber))
        //    {
                
        //    }
        //}
    
        private void PercentageButton_Click(object sender, RoutedEventArgs e)
        {
            double tempNumber;
            if (double.TryParse(resultLabel.Content.ToString(), out tempNumber))
            {
                tempNumber /= 100;
                if (lastNumber != 0)
                    tempNumber *= lastNumber;
                resultLabel.Content = tempNumber.ToString();
            }
        }
    
        private void NegativeButton_Click(object sender, RoutedEventArgs e)
        {
            if (double.TryParse(resultLabel.Content.ToString(), out lastNumber))
            {
                lastNumber *= -1;
                resultLabel.Content = lastNumber.ToString();
            }
        }
    
        private void AcButton_Click(object sender, RoutedEventArgs e)
        {
            resultLabel.Content = "0";
            result = 0;
            lastNumber = 0;
        }
    
        private void OperationButton_Click(object sender, RoutedEventArgs e)
        {
            if (double.TryParse(resultLabel.Content.ToString(), out lastNumber))
            {
                resultLabel.Content = 0;
            }
    
            if (sender == multiplyButton)
                selectedOperator = SelectedOperator.Multiplication;
            if (sender == divideButton)
                selectedOperator = SelectedOperator.Division;
            if (sender == plusButton)
                selectedOperator = SelectedOperator.Addition;
            if (sender == minusButton)
                selectedOperator = SelectedOperator.Subtraction;
    
        }
    
        private void dotButton_Click(object sender, RoutedEventArgs e)
        {
            if (resultLabel.Content.ToString().Contains("."))
            {
                // do nothing
            } else
            {
    
                resultLabel.Content = $"{resultLabel.Content}.";
            }
        }
    
        private void numberButton_Click(object sender, RoutedEventArgs e)
        {
            int selectedValue = int.Parse((sender as Button).Content.ToString());
    
            if(resultLabel.Content.ToString() == "0")
            {
                resultLabel.Content = $"{selectedValue}" ;
            } else
            {
                resultLabel.Content = $"{resultLabel.Content}{selectedValue}";
            }
        }


```c#
}

public enum SelectedOperator
{
    Addition,
    Subtraction,
    Multiplication,
    Division
}

public class SimpleMath
{
    public static double Add(double n1, double n2)
    {
        return n1 + n2;
    }
    public static double Subtraction(double n1, double n2)
    {
        return n1 - n2;
    }

    public static double Multiply(double n1, double n2)
    {
        return n1 * n2;
    }

    public static double Divide(double n1, double n2)
    {
        if (n2 == 0)
        {
            MessageBox.Show("Division by zero is not supperted", "Wrong operation", MessageBoxButton.OK, MessageBoxImage.Error);
            return 0;
        } 
        return n1 / n2;
    }
}
```
}