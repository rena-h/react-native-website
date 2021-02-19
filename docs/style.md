---
id: style
title: スタイル
---

React Native では、JavaScript を使ってアプリケーションをスタイリングします。全てのコアコンポーネントは `style` という名前の `prop` を受け取ります。スタイル名と [values](colors.md) は、`background-color` を `backgroundColor` のようにキャメルケースで記述すること以外、web 上の CSS の役割とほぼ同じです。

`style` という `prop` は 簡単な古い JavaScript オブジェクトです。 複数のスタイルを配列で渡すこともできます。配列内の最後のスタイルが優先されるので、スタイルを継承するために使うこともできます。

コンポーネントが複雑になってきた場合、1箇所で複数のスタイルを定義できる `StyleSheet.create` を使ってコードをきれいにします。以下に例をあげます。

```SnackPlayer name=Style
import React from 'react';
import { StyleSheet, Text, View } from 'react-native';

const LotsOfStyles = () => {
    return (
      <View style={styles.container}>
        <Text style={styles.red}>just red</Text>
        <Text style={styles.bigBlue}>just bigBlue</Text>
        <Text style={[styles.bigBlue, styles.red]}>bigBlue, then red</Text>
        <Text style={[styles.red, styles.bigBlue]}>red, then bigBlue</Text>
      </View>
    );
};

const styles = StyleSheet.create({
  container: {
    marginTop: 50,
  },
  bigBlue: {
    color: 'blue',
    fontWeight: 'bold',
    fontSize: 30,
  },
  red: {
    color: 'red',
  },
});

export default LotsOfStyles;
```

一般的な方法の1つは、 コンポーネントに `style` prop を受け取らせ、そしてそれが順番にサブコンポーネントにも使われるというものです。CSSと同じように、スタイルを "カスケード" させることができます。

テキストスタイルをカスタマイズする方法はもっと沢山あります。[テキストコンポーネントリファレンス](text.md) にその方法の一覧がまとまっています。

さてこれで、あなたはテキストの見た目をデザインできるようになりました。 スタイリングについてより詳しくなるため、次のステップに進みましょう。 [コンポーネントのサイズを調整する方法](height-and-width.md)