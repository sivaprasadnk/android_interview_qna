# 📌 **Kotlin Data Types – A Complete Guide**  

In Kotlin, every variable has a **type** that defines the kind of values it can hold. Kotlin has a **strongly typed** system, meaning that the compiler ensures type safety at compile time.  

---

## 🔹 **Basic Data Types in Kotlin**  

| **Type**  | **Size** | **Example** | **Description** |
|-----------|---------|-------------|-----------------|
| `Byte`    | 8-bit  | `val b: Byte = 127` | Smallest integer type (-128 to 127) |
| `Short`   | 16-bit | `val s: Short = 32000` | Small integer (-32,768 to 32,767) |
| `Int`     | 32-bit | `val i: Int = 2147483647` | Default integer type (-2^31 to 2^31-1) |
| `Long`    | 64-bit | `val l: Long = 9223372036854775807L` | Large integer (-2^63 to 2^63-1) |
| `Float`   | 32-bit | `val f: Float = 3.14f` | Floating-point number with 6-7 decimal digits |
| `Double`  | 64-bit | `val d: Double = 3.1415926535` | More precise floating-point number (15-16 digits) |
| `Boolean` | 1-bit  | `val isTrue: Boolean = true` | Holds `true` or `false` |
| `Char`    | 16-bit | `val c: Char = 'A'` | Stores a single character |
| `String`  | -      | `val str: String = "Hello"` | A sequence of characters |

---

## 🔹 **Number Types & Type Inference**  

Kotlin automatically infers types when declaring variables:  
```kotlin
val x = 100      // Inferred as Int
val y = 100L     // Inferred as Long
val z = 10.5     // Inferred as Double
val w = 10.5f    // Inferred as Float
```

To explicitly specify a type:  
```kotlin
val num: Long = 100L
val pi: Float = 3.14f
```

**📌 Note:** Use `L` for `Long` and `f` for `Float` to avoid type mismatches.

---

## 🔹 **Type Conversion**  

Kotlin does not support **implicit type conversion** (like Java). You must use explicit conversion functions:  

```kotlin
val num: Int = 100
val longNum: Long = num.toLong()  // Convert Int to Long
val doubleNum: Double = num.toDouble()  // Convert Int to Double
```

### **Available Conversion Functions:**  
| **Function**       | **Converts To** |
|--------------------|---------------|
| `toByte()`        | `Byte` |
| `toShort()`       | `Short` |
| `toInt()`         | `Int` |
| `toLong()`        | `Long` |
| `toFloat()`       | `Float` |
| `toDouble()`      | `Double` |
| `toChar()`        | `Char` |

---

## 🔹 **String Data Type**  

### **String Declaration:**  
```kotlin
val str1 = "Hello"
val str2 = "World"
val combined = str1 + " " + str2  // String concatenation
println(combined)  // Output: Hello World
```

### **Multiline Strings:**  
```kotlin
val multiLine = """
    This is
    a multiline
    string.
""".trimIndent()
println(multiLine)
```

### **String Interpolation:**  
```kotlin
val name = "Siva"
val age = 25
println("My name is $name and I am $age years old.")  
// Output: My name is Siva and I am 25 years old.
```

---

## 🔹 **Boolean Data Type**  

Boolean values can only be `true` or `false`.  
```kotlin
val isKotlinFun: Boolean = true
if (isKotlinFun) {
    println("Yes, Kotlin is fun!")
}
```

---

## 🔹 **Char Data Type**  

A `Char` holds a **single** character and is enclosed in **single quotes** (`' '`).  
```kotlin
val letter: Char = 'A'
val digit: Char = '5'
```

Characters can be checked using Unicode values:  
```kotlin
println(letter.code)  // Output: 65 (ASCII value of 'A')
```

---

## 🔹 **Arrays in Kotlin**  

Arrays store multiple values of the **same type**.  
```kotlin
val numbers = arrayOf(1, 2, 3, 4, 5)
println(numbers[0])  // Output: 1
```

To declare a specific type of array:  
```kotlin
val intArray = intArrayOf(1, 2, 3)
val doubleArray = doubleArrayOf(1.1, 2.2, 3.3)
```

---

## 🔹 **Nullable Types in Kotlin**  

By default, Kotlin does **not** allow `null` values to avoid `NullPointerException`.  
```kotlin
var name: String = "Kotlin"
// name = null  // ❌ Compilation Error
```

To allow `null`, use `?`:  
```kotlin
var name: String? = "Kotlin"
name = null  // ✅ Allowed
```

Using `!!` to force access:  
```kotlin
println(name!!.length)  // Throws NullPointerException if null
```

Using **Safe Call Operator (`?.`)**:  
```kotlin
println(name?.length)  // Prints null if name is null
```

Using **Elvis Operator (`?:`)**:  
```kotlin
val length = name?.length ?: 0  // If name is null, assign 0
```

---

## 📌 **Conclusion**  

Kotlin provides a **rich set of data types** to ensure **type safety, null safety, and better performance**. Understanding these is crucial for writing **clean and efficient** Kotlin code.  
