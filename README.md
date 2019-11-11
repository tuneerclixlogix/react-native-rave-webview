# Web View Wrapper for Rave by Flutterwave(https://rave.flutterwave.com/)
A web view wrapper for Flutterwave Rave payment gateway with support for React Native v0.60 and doesn't require any react native linking.

This package allows you plug-in Rave's payment gateway directly into your react native application and start accepting payment immediately.

This package copies a similar loading design to that of Rave, which makes transistion to Rave's website less noticeable. This package also offers a cancel button, so one can easily cancel if Rave takes a long time to load its content (the ``` onCancel ``` props event is called when this happens).

### Compatibility
|`@react-native-community/cli` |`react-native`|
| --| --|
|[^1.0.0](https://github.com/react-native-community/cli/tree/1.x) |^0.59.0|


### Integrating Rave React Native

You can pull in @creativejoe007/react-native-rave-webview into app with the steps below;

-   Change directory into your current project directory from your terminal and enter this command:

    > npm install @creativejoe007/react-native-rave-webview --save

## Usage

#### [](https://github.com/creativeJoe007/react-native-rave-webview#1--import-rave-component)1. import Rave Component

    import {RaveWebView} from '@creativejoe007/react-native-rave-webview';

 #### 2. Set your success, failure and close methods



    constructor(props) {
        super(props);

      }

      onSuccess(data) {
        console.log("success", data);
        // You get the complete response returned from FlutterWave,
        // just incase you need more than the reference number

      }

      onCancel() {
        console.log("error", 'Transaction was Cancelled!');
      }

      onError() {
        //an error occoured

      }
#### 3. Use component (ensure to set currency for the desired payment method to display)



     render() {
         return (
            <View  style={styles.container}>
              <RaveWebView
                buttonText=  "PAY NOW"
                raveKey="<your-api-key-here>"
                amount={20000}
                customerEmail={"team9.tech@gmail.com"}
                customerPhone={"08114089344"}
                billingEmail="team9.tech@gmail.com (optional)"
                billingMobile="08114089344 (optional)"
                billingName="Martins Joseph (optional but advised)"
                ActivityIndicatorColor="black"
                onCancel={this.onCancel}
                onSuccess={this.onSuccess}
                onError={() => { alert('something went wrong') }}
                btnStyles={{backgroundColor:'green', width:100, alignContent:  'center' }}
                textStyles={{ color:'white', alignSelf:  'center', }}
                txref="<your-autogenerated-transaction-reference>"
              />
            </View>
	    );
	   }



## API's



#### [](https://github.com/react-native-nigeria/react-native-rave-webview#API)all React-Native-rave-WebView API



| Name | use/description | extra |
| :--- | :---: | ---: |
| `buttonText` | Defines text on the button| `null` |
| `textStyles` | Defines styles for text in button | `null` |
| `btnStyles` | Defines style for button | `null` |
| `raveKey` | Public or Private FlutterWave Rave key(visit https://rave.flutterwave.com to get yours) |`null` |
| `amount` | Amount to be paid | `null` |
| `txref` | set TransactionRef for transaction | `null` |
| `ActivityIndicatorColor` | color of loader | default: `#f5a623` |
| `customerEmail` | Customer's email | default: `null` |
| `customerPhone` | Customer's Mobile | default: `null` |
| `billingEmail` | Billers email | default: `null` |
| `billingMobile` | Billers mobile | default: `null` |
| `billingName` | Billers Name | default: `null` |
| `onCancel` | callback function if user cancels, either while web view is loading or after loading | default: `null` |
| `onSuccess` | callback function if transaction was successful (it will return the entire response by Flutterwave's Rave ) | default: `null` |
| `onError` | callback function if an error occured during transaction  | default: `null` |



Everyone is welcome to create a pull request with detailed description of what it fixes, and I would ensure to test and merge.


  This project is licensed under ISC license.




### Don't forget to star, like and share :)
