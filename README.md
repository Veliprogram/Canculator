# Canculator
import Accelerate

func performLinearRegression() {
    print("Введите x-координаты (через запятую):")
    let x = readLine()!.split(separator: ",").compactMap{ Double($0) }
    
    print("Введите y-координаты (через запятую):")
    let y = readLine()!.split(separator: ",").compactMap{ Double($0) }
    
    var n = Int32(x.count)
    var a = [Double](repeating: 0, count: Int(n))
    var b = [Double](repeating: 0, count: Int(n))
    
    vDSP_vsmulD(x, 1, y, 1, &a, 1, n)
    vDSP_vsqD(x, 1, &b, 1, n)
    
    var slope: Double = 0
    var intercept: Double = 0
    
    vDSP_linear_regression(&a, 1, &b, 1, &slope, &intercept, &n)
    
    print("Уравнение прямой: y = \(slope) * x + \(intercept)")
}
