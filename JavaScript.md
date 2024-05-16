# JavaScript

- 配列操作メソッド

  - reduce()

    ```js
    const arr = [1, 2, 3, 4];

    const sum = arr.reduce((sum, num) => {
      return sum + num;
    }, 0);

    // 0はsumの初期値
    ```

  - concat()

    ```js
    const arr1 = ["a", "b", "c"];
    const arr2 = ["d", "e", "f"];
    const arr3 = arr1.concat(arr2);

    // arr3 = ["a", "b", "c", "d", "e", "f"];
    ```

  - structuredClone()
    - 多次元配列の場合、スプレッド構文ではネストされた配列はクローンされない。
    - `structuredClone()`はネストされた配列まで一気にクローン可能。

- ES Module

  - 便利な特徴
    - `'use strict';`を宣言せずに strict モードが適用される
    - `defer`がデフォルトで適用される
    - モジュール空間
    - import 文が使える
  - 注意点

    - ファイルの階層が同じでも明示する必要がある
      ```
      // 同一階層の foo.js を取得
      import foo from './foo.js';
      // 上の階層の bar.js を取得
      import bar from '../bar.js';
      // ルートパスの baz.js を取得
      import baz from '/baz.js';
      // 以下は無効
      import foo from 'foo.js';
      ```
    - webpack を導入しないと import 時のファイルの拡張子は省略不可
    - `var`は使用不可

  - サイドエフェクトインポート
    - ただファイルを実行する
    ```js
    import "./foo.js";
    ```

- localStorage

  - クライアントサイドでのみデータの使用が可能
  - 永続的にデータを保存する

  ```js
  localStorage.setItem("keyName", "value");
  localStorage.getItem("keyName");
  ```

  - 注意点
    - localStorage に set した値はすべて文字列に変換されるので、数字や真偽値を扱う際は注意する

- sessionStorage

  - クライアントサイドでのみデータの使用が可能
  - ブラウザを閉じるとデータは破棄される

- cookie
  - クライアントサイドとサーバーサイドの両方でデータの使用が可能
  - データの保存期間を設定できる