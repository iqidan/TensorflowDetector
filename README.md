# TensorflowDetector
Tensorflow android test

由于运行官方的Android功能总是失败,于是将官方核心代码抽取出来单独建立项目(github: https://github.com/tensorflow/tensorflow/tree/master/tensorflow/examples/android)

## 1 添加依赖
	打开build.gradle(Module:app)文件=>找到dependencies添加如下代码
```gradle
	implementation 'org.tensorflow:tensorflow-android:1.6.0'
```

	本工程的依赖如下
```gradle
	dependencies {
	    implementation fileTree(dir: 'libs', include: ['*.jar'])
	    implementation 'com.android.support:appcompat-v7:28.0.0'
	    implementation 'com.android.support.constraint:constraint-layout:1.1.3'
	    testImplementation 'junit:junit:4.12'
	    androidTestImplementation 'com.android.support.test:runner:1.0.2'
	    androidTestImplementation 'com.android.support.test.espresso:espresso-core:3.0.2'
	    implementation 'org.tensorflow:tensorflow-android:1.6.0'
	}
```

## 2 添加原来TensorFlow的Android工程里面的文件
	将org.tensorflow.demo下的文件拷贝到自己新建立的工程(我只需要图像识别, 所以没有将RecognizeCommands.java/SpeechActivity.java/StylizeActivity.java复制过来)
	(注意 需要修改包名引用问题)

	将res/layout文件,除了activity_speech.xml都复制过来

	将res/values中的strings.xml中的值复制过来

## 3 添加权限
	在AndroidManifest.xml添加如下代码:
```xml
	<uses-permission android:name="android.permission.CAMERA" />
    <uses-feature android:name="android.hardware.camera" />
    <uses-feature android:name="android.hardware.camera.autofocus" />
    <uses-permission android:name="android.permission.WRITE_EXTERNAL_STORAGE"/>
    <uses-permission android:name="android.permission.RECORD_AUDIO" />
```