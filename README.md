# Csnculator
func calculate(num1: Double, num2: Double, operation: String) -> Double {
    switch operation {
    case "+":
        return num1 + num2
    case "-":
        return num1 - num2
    case "x":
        return num1 * num2
    case "/":
        return num1 / num2
    default:
        return 0
    }
}


print("Введите первое число:")
let num1 = Double(readLine()!)!

print("Введите второе число:")
let num2 = Double(readLine()!)!

print("Выберите операцию (+, -, x, /):")
let operation = readLine()!


let result = calculate(num1: num1, num2: num2, operation: operation)
print("Результат: \(result)")
