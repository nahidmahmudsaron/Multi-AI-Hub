# 🚀 Multi AI Hub WebView Android App

একটি অ্যান্ড্রয়েড অ্যাপ্লিকেশন যা **TabLayout** এবং **Fragments** ব্যবহার করে জনপ্রিয় AI প্ল্যাটফর্মগুলো (ChatGPT, Gemini, Claude) একটি মাত্র অ্যাপের ভেতরে সহজ ও সুন্দরভাবে ব্যবহার করার সুযোগ তৈরি করে।

---

## 📌 প্রজেক্ট পরিচিতি (Description)

এই প্রজেক্টটি একটি **Native Android Application**। অ্যাপটিতে অ্যান্ড্রয়েডের `TabLayout` এবং `WebView` ব্যবহার করা হয়েছে, যার ফলে ব্যবহারকারী আলাদাভাবে ব্রাউজারে না গিয়ে একটি অ্যাপের মাধ্যমেই তিনটি AI অ্যাসিস্ট্যান্ট (ChatGPT, Gemini, Claude) ব্যবহার করতে পারবেন। 

### ✨ মূল বৈশিষ্ট্যসমূহ (Key Features):
* **Tab-Based Navigation:** অতি সহজে ট্যাব সুইচের মাধ্যমে আলাদা আলাদা AI ইন্টারফেসে যাওয়ার সুবিধা।
* **Fragment-Based Architecture:** প্রতিটি AI-এর জন্য আলাদা Fragment ব্যবহার করা হয়েছে যাতে কোড ক্লিন এবং মেইনটেইন করা সহজ হয়।
* **In-App Web Browsing:** `WebViewClient` ব্যবহারের মাধ্যমে অ্যাপের ভেতর থেকেই সরাসরি ওয়েবসাইট লোড করা হয়েছে, যা বাহ্যিক কোনো ব্রাউজার ওপেন হতে দেয় না।
* **Modern UI:** Material Design UI ব্যবহার করে তৈরি।

---

## 🛠️ ব্যবহৃত প্রযুক্তিসমূহ (Technologies Used)

* **Language:** Java
* **UI Components:** Android Material Components (`TabLayout`, `Fragment`, `WebView`, `LinearLayout`)
* **IDE:** Android Studio

---

## 📜 প্রজেক্টের সমস্ত কোড (Project Source Code)

নিচে এই প্রজেক্টে ব্যবহৃত সমস্ত XML এবং Java কোড দেওয়া হলো:

### 1️⃣ AndroidMain.xml
```xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout android:background="#FFFFFF" android:id="@+id/main" android:layout_height="match_parent" android:layout_width="match_parent" android:orientation="vertical" tools:context=".MainActivity" xmlns:android="[http://schemas.android.com/apk/res/android](http://schemas.android.com/apk/res/android)" xmlns:app="[http://schemas.android.com/apk/res-auto](http://schemas.android.com/apk/res-auto)" xmlns:tools="[http://schemas.android.com/tools](http://schemas.android.com/tools)">

    <com.google.android.material.tabs.TabLayout
        android:id="@+id/tabLayout"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        app:tabIndicatorColor="#27ae60"
        app:tabIndicatorFullWidth="true"
        app:tabSelectedTextColor="#27ae60"
        app:tabTextColor="#FF5722">

        <com.google.android.material.tabs.TabItem
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="ChatGPT" />

        <com.google.android.material.tabs.TabItem
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="Gemini" />

        <com.google.android.material.tabs.TabItem
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="Claude" />
    </com.google.android.material.tabs.TabLayout>

    <!-- Fragment দেখানোর জন্য FrameLayout -->
    <FrameLayout android:id="@+id/framelayout" android:layout_height="match_parent" android:layout_width="match_parent"/>

</LinearLayout>


### 1️⃣ Fregment.Java
```java
package com.example.webviewproject;

import android.os.Bundle;
import androidx.fragment.app.Fragment;
import android.view.LayoutInflater;
import android.view.View;
import android.view.ViewGroup;
import android.webkit.WebView;
import android.webkit.WebViewClient;

public class GeminiFragment extends Fragment {

    WebView webView;

    @Override
    public View onCreateView(LayoutInflater inflater, ViewGroup container, Bundle savedInstanceState) {
        // ১. Layout ইনফ্লেট করা
        View myView = inflater.inflate(R.layout.fragment_gemini, container, false);

        // ২. WebView চিহ্নিত করা
        webView = myView.findViewById(R.id.webView);

        // ৩. WebView সেটিংস কনফিগার করা
        webView.getSettings().setJavaScriptEnabled(true);
        webView.setWebViewClient(new WebViewClient());
        webView.loadUrl("[https://gemini.google.com](https://gemini.google.com)");

        return myView;
    }
}


### 1️⃣ Fregment.Java





