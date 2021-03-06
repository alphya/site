# C++20

## 概要
C++20とは、2020年中に改訂される予定の、C++バージョンの通称である。

このバージョンは、策定中はC++2aと呼ばれることがあった。「202a年にリリースされる」という伏せ字として「a」が使われているが、3年周期に次のバージョンが策定されることが決まっているため、伏せ字になっている年数がずれることはない。


## 言語機能
### クラス
| 言語機能 | 説明 |
|----------|------|
| 指示付き初期化 | |
| [一貫比較](cpp20/consistent_comparison.md.nolink) | |
| [契約に基づくプログラミング](cpp20/contract-based_programming.md.nolink) | 事前条件、事後条件、表明を宣言する新たな属性構文を追加 |
| [ビットフィールドのメンバ変数初期化](cpp20/default_member_initializers_for_bit_fields.md) | ビットフィールドメンバ変数のデフォルト値を設定する構文を追加する |
| [コンストラクタを条件付きで`explicit`にする構文を追加](cpp20/explicit_bool.md.nolink) | `explicit(true)`のように`explicit`に真理値パラメータを指定できるようにする |
| [`const`修飾されたメンバポインタの制限を修正](cpp20/fixing_const_qualified_pointers_to_members.md) | `.*`演算子での左辺値の`const`メンバ関数呼び出しを許可する |
| デフォルトのコピーコンストラクタと非`const`なコンストラクタが衝突する問題を修正 | |
| 特殊化のアクセスチェック | |
| [空オブジェクトを言語サポート](cpp20/language_support_for_empty_objects.md.nolink) | `[[no_unique_address]]`属性を導入し、空の型のオブジェクトをほかのオブジェクトと共有する最適化を許可する |
| [friend指定された関数内から構造化束縛を使用して非公開メンバ変数にアクセスすることを許可](cpp20/allow_structured_bindings_to_accessible_members.md) | 構造化束縛の仕様として公開メンバ変数のみを取り出せるようになっていたが、friend指定された関数からは非公開メンバ変数にもアクセスできるようにする |
| [構造化束縛がカスタマイゼーションポイントを見つけるルールを緩和](cpp20/relaxing_the_structured_bindings_customization_point_finding_rules.md) | 非テンプレートの`get()`メンバ関数が見つかった場合は、非メンバ関数の`get()`を探しにいく |
| [抽象型のチェック](cpp20/checking_for_abstract_class_types.md.nolink) | 関数の宣言段階では、パラメータおよび戻り値型が抽象型かどうかをチェックしないようにする | | | | |
| [可変長データを扱うクラスの効率的な`delete`](cpp20/efficient_sized_delete_for_variable_sized_classes.md.nolink) | クラスの`delete`演算子が呼び出される前にデストラクタが呼ばれないようにするオプションを追加 |


### 整数

| 言語機能 | 説明 |
|----------|------|
| [符号付き整数型が2の補数表現であることを規定](cpp20/signed_integers_are_twos_complement.md.nolink) | 処理系が2の補数以外をサポートしていなかったこともあり、現実に即した規定とする |


### 文字列

| 言語機能 | 説明 |
|----------|------|
| [UTF-8エンコーディングされた文字の型として`char8_t`を追加](cpp20/char8_t.md.nolink) | UTF-8エンコードされた文字かどうかでオーバーロード・特殊化をできるようにする |


### 制御構文

| 言語機能 | 説明 |
|----------|------|
| [初期化式をともなう範囲for文](cpp20/range-based_for_statements_with_initializer.md) | 範囲for文スコープで使用する変数の初期化のための構文を追加 |
| [範囲for文がカスタマイゼーションポイントを見つけるルールを緩和](cpp20/relaxing_the_range_for_loop_customization_point_finding_rules.md) | `begin()`/`end()`メンバ関数のどちらかが見つからなかった場合に非メンバ関数の`begin()`/`end()`を探しにいく |
| [当たる確率が高い分岐と、当たる確率が低い分岐をコンパイラに伝える属性を追加](cpp20/likely_and_unlikely_attributes.md.nolink) | コンパイラが分岐予測するためのヒントとする |


### テンプレート

| 言語機能 | 説明 |
|----------|------|
| コンセプト | |
| [型の文脈で`typename`の省略を許可](cpp20/down_with_typename.md.nolink) | 型しか現れない文脈では、依存名を解決するための`typename`キーワードを省略できるようにする |
| [非型テンプレートパラメータとしてクラス型を許可する](cpp20/class_types_in_non-type_template_parameters.md.nolink) | `std::strong_equality`に変換可能な非メンバ関数`<=>`をもつ型を、非型テンプレートパラメータとして使用できるようにする |
| 関数テンプレートに明示的に型指定した場合にADLで見つからない問題を修正 | |


### 定数式

| 言語機能 | 説明 |
|----------|------|
| 評価されない文脈で`constexpr`関数が定数式評価されることを規定 | |
| [定数式からの仮想関数の呼び出しを許可](cpp20/allow_virtual_function_calls_in_constant_expressions.md) | 仮想関数に`constexpr`を付けられない制限を解除 |
| [定数式での`dynamic_cast`、多態的な`typeid`を許可](cpp20/allowing_dynamic_cast_polymorphic_typeid_in_constant_expressions.md.nolink) | 定数式での動的多態を許可 |
| [constexpr関数内でのtry-catchブロックを許可](cpp20/try-catch_blocks_in_constexpr_functions.md.nolink) | constexpr関数内での例外の捕捉を許可する |
| [即時関数](cpp20/immediate_functions.md.nolink) | `consteval`キーワードを追加し、常に定数式評価されるよう指定できるようにする |
| [定数式内での共用体のアクティブメンバの変更を許可](cpp20/changing_the_active_member_of_a_union_inside_constexpr.md.nolink) | 共用体メンバの書き換えを定数式内で行えるようにする |


### ラムダ式

| 言語機能 | 説明 |
|----------|------|
| [ジェネリックラムダのテンプレート構文](cpp20/familiar_template_syntax_for_generic_lambdas.md) | ジェネリックラムダでテンプレートパラメータを定義できるようにする |
| [ラムダ式のキャプチャとして`[=, this]`を許可する](cpp20/allow_lambda_capture_equal_this.md) | デフォルトコピーキャプチャと`this`ポインタのコピーキャプチャを両方指定できるようにする |
| [`[=]`による`this`の暗黙のキャプチャを非推奨化](cpp20/deprecate_implicit_capture_of_this_via_defcopy.md) | コピーのデフォルトキャプチャでは、`this`ポインタをキャプチャされなくする |
| ラムダ式の制約 | |
| 暗黙のラムダキャプチャを簡略化 | |
| 状態を持たないラムダ式を、デフォルト構築可能、代入可能とする | |
| 評価されない文脈でのラムダ式 | |
| [ラムダ式の初期化キャプチャでのパック展開を許可](cpp20/allow_pack_expansion_in_lambda_init_capture.md.nolink) | `[...args = std::move(args)]`のようなキャプチャを許可 |


### 名前空間

| 言語機能 | 説明 |
|----------|------|
| [入れ子名前空間定義でのインライン名前空間](cpp20/nested_inline_mamespaces.md.nolink) | `namespace ns1::inline ns2::ns3 {}`のように、入れ子名前空間を定義する式にインライン名前空間の指定を含められるようにする |


### プリプロセッサ

| 言語機能 | 説明 |
|----------|------|
| [可変引数が空でない場合のトークン置換](cpp20/va_opt.md) | プリプロセッサの置換で可変引数が空の場合に余計なカンマが付いてしまう問題に対処 |



### 機能の非推奨化

| 言語機能 | 説明 |
|----------|------|
| PODを非推奨化 | |
| [`[=]`による`this`の暗黙のキャプチャを非推奨化](cpp20/deprecate_implicit_capture_of_this_via_defcopy.md) | コピーのデフォルトキャプチャでは、`this`ポインタをキャプチャされなくする |


### 機能の削除

| 言語機能 | 説明 |
|----------|------|
| `throw()`による例外送出しない指定を削除 | 代わりに`noexcept`を使用すること |
| [ユーザー宣言したコンストラクタを持つクラスの集成体初期化を禁止](cpp20/prohibit_aggregates_with_user-declared_constructors.md.nolink) | コンストラクタが`delete`宣言されているクラスを、集成体初期化によってコンストラクタ呼び出しを回避して構築できてしまっていた技法を禁止 |


### 小さな変更

| 言語機能 | 説明 |
|----------|------|
| [Unicode標準への参照を更新](cpp20/update_the_reference_to_the_unicode_standard.md.nolink) | 標準C++からISO/IEC 10646への参照を更新し、古い固定バージョンへの参照をやめる |



## ライブラリ更新の概要
### 新ライブラリ
- [`<version>`](/reference/version.md)ヘッダを新設する。ここでは、実装依存の情報 (バージョンやリリース日付など) が標準ライブラリの実装によって定義される
- [`<chrono>`](/reference/chrono.md)ヘッダに、カレンダーとタイムゾーンの機能を拡張
- 任意のシーケンスの部分シーケンスを参照するライブラリとして[`<span>`](/reference/span.md.nolink)を追加
- 出力ストリームを同期するライブラリとして[`<syncstream>`](/reference/syncstream.md.nolink)を追加
- [`<compare>`](/reference/compare.md.nolink)ヘッダを新設する。ここでは、一貫比較 (宇宙船演算子) をサポートするための型と比較関数が定義される
- [`<bit>`](/reference/bit.md)ヘッダを新設する
    - Strict Aliasing規則に抵触しないビットレベルの再解釈キャストである[`std::bit_cast()`](/reference/bit/bit_cast.md)関数を追加
    - 2の乗数関係の関数として、整数値が2の累乗かを判定する[`std::ispow2()`](/reference/bit/ispow2.md)関数、整数値を2の累乗値に切り上げる[`std::ceil2()`](/reference/bit/ceil2.md)関数、整数値を2の累乗値に切り下げる[`std::floor2()`](/reference/bit/floor2.md)関数、2を底とした整数値の対数を求めて1を足す[`std::log2p1()`](/reference/bit/log2p1.md)関数を追加
- 型制約のための要件ライブラリとして[`<concepts>`](/reference/concepts.md)を追加


### 取り決め
- `std`名前空間以下の関数テンプレートをユーザーが特殊化することを禁止する (参照 : [P0551R3](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0551r3.pdf))


### コンテナ
- 連想コンテナに、要素がコンテナに含まれているかを判定する`contains()`メンバ関数を追加
- [`std::forward_list`](/reference/forward_list/forward_list.md)と[`std::list`](/reference/list/list.md)のメンバ関数`remove()`、`remove_if()`、`unique()`の戻り値型を、`void`から`Container::size_type`に変更


### アルゴリズム
- [`<algorithm>`](/reference/algorithm.md)の検索、ソート関係に`constexpr`を追加
- [`<algorithm>`](/reference/algorithm.md)に、要素位置をシフトする[`std::shift_left()`](/reference/algorithm/shift_left.md.nolink)、[`std::shift_right()`](/reference/algorithm/shift_right.md.nolink)を追加
- 一貫比較への対応のため、[`<algorithm>`](/reference/algorithm.md)に[`std::lexicographical_compare_3way()`](/reference/algorithm/lexicographical_compare_3way.md.nolink)および[`std::compare_3way()`](/reference/algorithm/compare_3way.md.nolink)を追加
- [`<numeric>`](/reference/numeric.md)の数値計算アルゴリズムをムーブに対応


### 文字列
- [`std::basic_string`](/reference/string/basic_string.md)クラスと[`std::basic_string_view`](/reference/string_view/basic_string_view.md)クラスに、先頭の部分文字列を判定する`starts_with()`メンバ関数、末尾の部分文字列を判定する`ends_with()`メンバ関数を追加


### 並行処理
- [`std::atomic`](/reference/atomic/atomic.md)クラスのスマートポインタに対する特殊化を追加
- [`std::atomic`](/reference/atomic/atomic.md)クラスの浮動小数点数型に対する特殊化を追加
- [`std::memory_order`](/reference/atomic/memory_order.md)の列挙子にスコープをもたせた
- 非アトミックな型にアトミック操作を適用するためのクラス[`std::atomic_ref`](/reference/atomic/atomic_ref.md.nolink)を追加


### 入出力
- 同期ストリームの追加にともなって、[`<ostream>`](/reference/ostream.md)に、同期ストリーム関係の出力マニピュレータを追加


### スマートポインタ
- [`std::make_shared()`](/reference/memory/make_shared.md)と[`std::allocate_shared()`](/reference/memory/allocate_shared.md)を配列に対応
- ポインタを生ポインタに変換する[`std::to_address()`](/reference/memory/to_address.md)を追加


### ユーティリティ
- [`std::exchange()`](/reference/utility/exchange.md)関数に`constexpr`を追加
- [`std::complex`](/reference/complex/complex.md)クラスを`constexpr`に対応


### 型特性
- [`<type_traits>`](/reference/type_traits.md)に、constexpr関数が定数式評価されたかを判定する特殊な関数[`std::is_constant_evaluated()`](/reference/type_traits/is_constant_evaluated.md.nolink)を追加
- [`<type_traits>`](/reference/type_traits.md)に、エンディアンを表す列挙型として[`std::endian`](/reference/type_traits/endian.md)を追加
- [`<type_traits>`](/reference/type_traits.md)に、型のCV修飾と参照を除去する型特性クラスとして[`std::remove_cvref`](/reference/type_traits/remove_cvref.md)を追加
- [`<type_traits>`](/reference/type_traits.md)に、受け取った型をそのまま返す[`std::type_identity`](/reference/type_traits/type_identity.md.nolink)を追加
- [`<type_traits>`](/reference/type_traits.md)に、例外送出せずに暗黙の型変換が可能かを判定する[`std::is_nothrow_convertible`](/reference/type_traits/is_nothrow_convertible.md.nolink)を追加


### 機能の非推奨化
- 一貫比較機能にとって比較演算子の定義が容易になったため、不要になった演算子の簡潔定義機能である[`std::rel_ops`](/reference/utility/rel_ops.md)を非推奨化


### 機能の削除
- C++11で[`allocator_traits`](/reference/memory/allocator_traits.md)クラスが導入されたことでC++17から非推奨化されていた、[`allocator`](/reference/memory/allocator.md)の以下のメンバを削除：
    - `size_type`型
    - `difference_type`型
    - `pointer`型
    - `const_pointer`型
    - `reference`型
    - `const_reference`型
    - `rebind`型
    - [`address()`](/reference/memory/allocator/address.md)メンバ関数
    - [`allocate()`](/reference/memory/allocator/allocate.md)メンバ関数の`hint`パラメータ
    - [`max_size()`](/reference/memory/allocator/max_size.md)メンバ関数
    - [`construct()`](/reference/memory/allocator/construct.md)メンバ関数
    - [`destroy()`](/reference/memory/allocator/destroy.md)メンバ関数
- C++11で[`allocator_traits`](/reference/memory/allocator_traits.md)クラスが導入されたことでC++17から非推奨化されていた、要素型を再束縛するための`allocator<void>`特殊化を非推奨化
- C++17で非推奨化されていた、`constexpr`で扱える型の分類である[`is_literal_type`](/reference/type_traits/is_literal_type.md)型特性を削除
- C++17で非推奨化されていた、一時的なメモリ確保のための[`std::get_temporary_buffer()`](/reference/memory/get_temporary_buffer.md)関数と[`std::return_temporary_buffer()`](/reference/memory/return_temporary_buffer.md)関数を削除
- C++17で非推奨化されていた[`raw_storage_iterator`](/reference/memory/raw_storage_iterator.md)クラスを削除
- [`not_fn()`](/reference/functional/not_fn.md)の追加にともない、C++17から非推奨化されていた以下の機能を削除：
    - [`not1()`](/reference/functional/negators.md)関数
    - [`not2()`](/reference/functional/negators.md)関数
    - [`unary_negate`](/reference/functional/negators.md)クラス
    - [`binary_nagate`](/reference/functional/negators.md)クラス
    - 標準関数オブジェクトの`result_type`、`argument_type`、`first_argument_type`、`second_argument_type`型
- C++17から非推奨化されていた[`shared_ptr`](/reference/memory/shared_ptr.md)`::`[`unique()`](/reference/memory/shared_ptr/unique.md)を削除
- [`invoke_result`](/reference/type_traits/invoke_result.md.nolink)の追加にともない、C++17から非推奨化されていた[`result_of`](/reference/type_traits/result_of.md)を削除
- C++17での[`uncaught_exceptions()`](/reference/exception/uncaught_exceptions.md.nolink)の追加にともない、非推奨化していた[`uncaught_exception()`](/reference/exception/uncaught_exception.md)を削除

