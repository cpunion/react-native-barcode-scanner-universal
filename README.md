# react-native-barcode-scanner-universal

Just combine `react-native-barcodescanner` and `react-native-camera`.

## Install

**Install library**

`npm install --save react-native-barcode-scanner-universal`

**Link native libraries of `react-native-barcodescanner` and `react-native-camera`**

```
which rnpm || npm install -g rnpm
rnpm link
```

**Also can link manually**

See:
* https://github.com/lwansbrough/react-native-camera#manual-install
* https://github.com/ideacreation/react-native-barcodescanner#installation

## Usage

```js
import BarcodeScanner from 'react-native-barcode-scanner-universal'

render: function () {
  let scanArea = null
  if (Platform.OS === 'ios') {
    scanArea = (
      <View style={styles.rectangleContainer}>
        <View style={styles.rectangle} />
      </View>
    )
  }

  <BarcodeScanner
    onBarCodeRead={(code) => console.log(code)}
    style={styles.camera}>
    {scanArea}
  </BarcodeScanner>
}

const styles = StyleSheet.create({
  camera: {
    flex: 1
  },
  rectangleContainer: {
    flex: 1,
    alignItems: 'center',
    justifyContent: 'center',
    backgroundColor: 'transparent'
  },
  rectangle: {
    height: 250,
    width: 250,
    borderWidth: 2,
    borderColor: '#00FF00',
    backgroundColor: 'transparent'
  }
})
```

## License

MIT.
