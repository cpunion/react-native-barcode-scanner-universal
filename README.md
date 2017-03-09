# [DEPRECATED] Please use react-native-camera

# react-native-barcode-scanner-universal

Just combine `react-native-barcodescanner` and `react-native-camera`, because `react-native-barcodescanner` provides Android version, `react-native-camera` provides iOS version.

## Install

**Install library**

`npm install --save react-native-barcode-scanner-universal`

***----------- IMPORTANT ------------***

**Link native libraries of `react-native-barcodescanner` and `react-native-camera`**

```
which rnpm || npm install -g rnpm
rnpm link react-native-camera
rnpm link react-native-barcodescanner
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

  return (
    <BarcodeScanner
      onBarCodeRead={(code) => console.log(code)}
      style={styles.camera}>
      {scanArea}
    </BarcodeScanner>
  )
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
