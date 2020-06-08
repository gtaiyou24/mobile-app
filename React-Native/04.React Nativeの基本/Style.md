 - https://reactnative.dev/docs/style


# スタイル
```js
import React from 'react';
import { StyleSheet, Text, View } from 'react-native';

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

export default LotsOfStyles = () => {
    return (
      <View style={styles.container}>
        <Text style={styles.red}>just red</Text>
        <Text style={styles.bigBlue}>just bigBlue</Text>
        <Text style={[styles.bigBlue, styles.red]}>bigBlue, then red</Text>
        <Text style={[styles.red, styles.bigBlue]}>red, then bigBlue</Text>
      </View>
    );
}
```

# Height and Width
```js
import React, { Component } from 'react';
import { View } from 'react-native';

export default function FixedDimensionsBasics() {
    return (
      <View>
        <View style={{width: 50, height: 50, backgroundColor: 'powderblue'}} />
        <View style={{width: 100, height: 100, backgroundColor: 'skyblue'}} />
        <View style={{width: 150, height: 150, backgroundColor: 'steelblue'}} />
      </View>
    );
}
```

`flex`コンポーネントのスタイルで使用して、使用可能なスペースに基づいてコンポーネントを動的に拡大および縮小します。通常は、`flex: 1`を使用します。これは、使用可能なすべてのスペースを埋めるようにコンポーネントに指示し、同じ親を持つ他のコンポーネント間で均等に共有します。
```js
import React, { Component } from 'react';
import { View } from 'react-native';

export default function FlexDimensionsBasics() {
    return (
      // Try removing the `flex: 1` on the parent View.
      // The parent will not have dimensions, so the children can't expand.
      // What if you add `height: 300` instead of `flex: 1`?
      <View style={{flex: 1}}>
        <View style={{flex: 1, backgroundColor: 'powderblue'}} />
        <View style={{flex: 2, backgroundColor: 'skyblue'}} />
        <View style={{flex: 3, backgroundColor: 'steelblue'}} />
      </View>
    );
}
```

# Layout with Flexbox
https://reactnative.dev/docs/flexbox

# Images
https://reactnative.dev/docs/images

# Color Reference
https://reactnative.dev/docs/colors
