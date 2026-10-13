# Android Studio ছাড়া APK তৈরি

এই সোর্স ZIP-এ `.github/workflows/build-apk.yml` যুক্ত করা হয়েছে। GitHub Actions-এ Android SDK ও Gradle ইনস্টল করে debug APK তৈরির চেষ্টা স্বয়ংক্রিয় হবে।

## ধাপ
1. GitHub.com-এ নিজের অ্যাকাউন্টে সাইন ইন করুন।
2. একটি নতুন **private repository** তৈরি করুন (যেমন `vdp-mouza-map`)।
3. এই ZIP ফাইলটি Extract করে এর ভেতরের সব ফাইল ও `.github` ফোল্ডারসহ repository-তে upload/commit করুন। `.github` ফোল্ডারটি যেন বাদ না যায়।
4. Repository-র **Actions** ট্যাবে যান। `Build VDP Mouza APK` workflow নির্বাচন করে **Run workflow** চাপুন; অথবা `main` branch-এ ফাইল push হলে workflow স্বয়ংক্রিয়ভাবে চলবে।
5. কাজ সফল হলে workflow run-এর পৃষ্ঠার **Artifacts** অংশ থেকে `VDP-Mouza-debug-APK` ডাউনলোড করুন এবং ZIP extract করে `app-debug.apk` ফাইলটি Android ফোনে পাঠান।
6. ফোনে APK খুলুন। প্রয়োজনে Android Settings-এ ওই অ্যাপ/ফাইল ম্যানেজারের জন্য “Install unknown apps” অনুমতি দিন। শুধু নিজের তৈরি/বিশ্বস্ত APK ইনস্টল করুন।

## গুরুত্বপূর্ণ
- এটি **debug APK**; Play Store-এ প্রকাশের জন্য signed release APK আলাদাভাবে তৈরি করতে হবে।
- এই workflow বিল্ড করার চেষ্টা স্বয়ংক্রিয় করে; প্রকল্পের compile error থাকলে Actions log-এ তা দেখাবে এবং কোড সংশোধন দরকার হবে।
- অনলাইন Satellite imagery-র জন্য একটি উপযুক্ত টাইল উৎস/লাইসেন্স দরকার হতে পারে। অফলাইন স্যাটেলাইট ছবি এই workflow একা যোগ করে না।
