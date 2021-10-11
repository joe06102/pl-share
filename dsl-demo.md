---
layout: two-cols
---

<style>
.col-left {
    margin-right: 12px;
}

.col-right {
    margin-left: 12px;
}
</style>

```js
Page({
    data() {
        return {
            title: 'hello world'
        }
    },
    onClick() {
        alert(this.data.title)
    }
})
```

```html
<view>
    <text>{{ title }}</text>
</view>
```

::right::

```jsx
import { View, Text } from 'react-native'
import createReactClass from 'create-react-class'

export default createReactClass({
    getInitialState() {
        return {
            title: 'hello world'
        }
    },
    onClick() {
        alert(this.state.title)
    }    
    render() {
        return (
            <View>
                <Text>{this.state.title}</Text>
            </View>
        )
    }
})
```
