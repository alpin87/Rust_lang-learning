# Rust_lang-learning

Cargo.toml가 없을시 실행 X






챕터 5 )

# Rust 열거형, 옵션, match 제어 흐름, if let

## 1. Enum (열거형)

Rust에서 열거형은 여러 가능한 변종을 가질 수 있는 데이터 타입을 정의하는 데 사용됩니다.

```rust
enum Message {
    Quit,
    Move { x: i32, y: i32 },
    Write(String),
    ChangeColor(i32, i32, i32),
}


Message 열거형에는 Quit, Move, Write, ChangeColor의 네 가지 변종이 있으며, 각 변종은 다른 타입의 데이터를 가질 수 있습니다.


2. Option<T>
Rust에서 Option<T> 열거형은 값이 있거나 없을 수 있는 상황을 표현하는 데 사용됩니다. 이는 다른 언어에서 null을 사용하는 것과 유사하지만, Rust에서는 Option<T>를 사용하여 명시적으로 처리해야 합니다.

enum Option<T> {
   None,
   Some(T),
}

Option<T> 열거형에는 Some(T)와 None의 두 가지 변종이 있습니다. Some(T)는 어떤 값 T를 가지며, None은 값이 없음을 나타냅니다.

let number: Option<i32> = Some(5);
let no_number: Option<i32> = None;

위 코드는 Option<T>를 사용하여 정수 값이 있을 수도 있고 없을 수도 있는 상황을 표현합니다.

3. match 제어 흐름
match 표현식은 열거형의 값을 패턴 매칭을 통해 분기하며, 모든 경우를 처리해야 합니다.

let optional = Some(5);

match optional {
    Some(i) => println!("값은 {}입니다.", i),
    None => println!("값이 없습니다."),
}

match 표현식은 optional 값이 Some(i)인지 None인지를 확인하고, 각 경우에 대해 다른 코드를 실행합니다.

4. if let 제어 흐름
if let은 match의 간결한 버전입니다. 특정 패턴에만 관심이 있고 다른 경우는 무시하고 싶을 때 사용됩니다.

let optional = Some(5);

if let Some(i) = optional {
    println!("값은 {}입니다.", i);
}

if let 표현식은 optional 값이 Some(i)인 경우에만 코드를 실행하며, None인 경우는 무시합니다. match와 달리 if let은 모든 경우를 처리하지 않아도 됩니다.

모든 경우를 처리해야 할 때는 match를 사용하고, 특정 패턴에만 관심이 있을 때는 if let을 사용하면 됩니다.
