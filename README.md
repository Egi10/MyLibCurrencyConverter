<p align="center">
  <img src="https://github.com/gzeinnumer/MyLibUtils/blob/master/preview/bg.jpg" width="400"/>
</p>

<h1 align="center">
    MyLibUtils
</h1>

<p align="center">
    <a><img src="https://img.shields.io/badge/Version-1.0.0-brightgreen.svg?style=flat"></a>
    <a><img src="https://img.shields.io/badge/ID-gzeinnumer-blue.svg?style=flat"></a>
    <a><img src="https://img.shields.io/badge/Java-Suport-green?logo=java&style=flat"></a>
    <a><img src="https://img.shields.io/badge/Koltin-Suport-green?logo=kotlin&style=flat"></a>
    <a href="https://github.com/gzeinnumer"><img src="https://img.shields.io/github/followers/gzeinnumer?label=follow&style=social"></a>
    <br>
    <p>Simple function for <b>Date</b> and <b>String</b>.</p>
</p>

---
## Download
Add maven `jitpack.io` and `depedencies` in build.gradle (Project) :
```gradle
// build.gradle project
allprojects {
  repositories {
    ...
    maven { url 'https://jitpack.io' }
  }
}

// build.gradle app/module
dependencies {
  ...
  implementation 'com.github.gzeinnumer:MyLibCurrencyConverter:version'
}
```

## Feature List
- [x] **CurrencyConverter**.

## Tech stack and 3rd library
- TextWatcher ([docs](https://developer.android.com/reference/android/text/TextWatcher))

---
## Use

### CurrencyConverter.
> **Java**
```
//sample 1
//get real value from input via onclick
editText.addTextChangedListener(new CurrencyConverter(editText));

button.setOnClickListener(new View.OnClickListener() {
    @Override
    public void onClick(View v) {
        String str = editText.getText().toString();
        Log.d(TAG, "onClick: "+CurrencyConverter.trimCommaOfString(str));
        Log.d(TAG, "onClick: "+editText.getText().toString());
    }
});

//sample 2
//get real value from input via listener
editText.addTextChangedListener(new CurrencyConverter(editText, new CurrencyConverter.StringCallBack() {
    @Override
    public void realString(String value) {
        Log.d(TAG, "realString: "+value);
        Log.d(TAG, "realString: "+editText.getText().toString());
    }
}));
```
> **Kotlin**
```kotlin
//sample 1
//get real value from input via onclick
editText.addTextChangedListener(CurrencyConverter(editText))
button.setOnClickListener {
    val str: String = editText.text.toString()
    Log.d(TAG, "onClick: " + CurrencyConverter.trimCommaOfString(str))
    Log.d(TAG, "onClick: "+editText.text.toString())
}

//sample 2
//get real value from input via listener
editText.addTextChangedListener(
    CurrencyConverter(editText,
        StringCallBack { value ->
            Log.d(TAG, "realString: $value")
            Log.d(TAG, "realString: "+editText.text)
        }
    )
)
```

---

```
Copyright 2020 M. Fadli Zein
```