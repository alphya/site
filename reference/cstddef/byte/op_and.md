# operator&
* cstddef[meta header]
* std[meta namespace]
* function[meta id-type]
* cpp17[meta cpp]

```cpp
namespace std {
  constexpr byte operator&(byte l, byte r) noexcept;
}
```

## 概要
`byte`型の値をビット論理積する。


## 効果
以下の式と同等の効果をもつ：

```cpp
return static_cast<byte>(static_cast<unsigned char>(static_cast<unsigned int>(l) & static_cast<unsigned int>(r)));
```


## 例外
投げない


## 例
```cpp example
#include <cassert>
#include <cstddef>

int main()
{
  std::byte a{0b0000'0011};
  std::byte b{0b0000'0101};

  std::byte result = a & b;

  assert(static_cast<unsigned char>(result) == 0b0000'0001);
}
```

### 出力
```
```

## バージョン
### 言語
- C++17

### 処理系
- [Clang, C++17 mode](/implementation.md#clang): 5.0
- [GCC, C++17 mode](/implementation.md#gcc): 7.1
- [Visual C++](/implementation.md#visual_cpp): ??


## 参照
- [LWG Issue 2950. `std::byte` operations are misspecified](https://wg21.cmeerw.net/lwg/issue2950)
