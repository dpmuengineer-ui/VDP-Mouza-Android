# VDP Mouza Map — Android source project

এই প্রজেক্টে আপলোড করা KMZ ফাইল থেকে ২৩টি Mouza boundary-কে GeoJSON-এ এবং ২২টি LULC GroundOverlay-কে স্থানীয় PNG asset-এ রূপান্তর করা হয়েছে।

## গুরুত্বপূর্ণ সীমাবদ্ধতা
- এটি Android Studio source project; এই পরিবেশে APK build/test করা হয়নি।
- বর্তমানে Leaflet JavaScript/CSS CDN থেকে লোড হয়, তাই প্রথমবার ম্যাপ ইঞ্জিন লোড করতে ইন্টারনেট প্রয়োজন।
- OpenStreetMap street basemap এবং Esri World Imagery (satellite) অনলাইন টাইল ব্যবহার করে। Google API key লাগে না, তবে Esri/OSM-এর attribution ও ব্যবহারের শর্ত মানতে হবে।
- “No basemap” নির্বাচন করলে বেস টাইল বন্ধ হয়; কিন্তু Leaflet CDN-ও offline হলে অ্যাপের ম্যাপ UI চালু হবে না। পূর্ণ offline operation-এর পরবর্তী ধাপে Leaflet-কে local assets-এ bundle করতে হবে এবং বৈধ offline basemap tiles যোগ করতে হবে।
- Esri imagery-কে “open data” বলে দাবি করা হচ্ছে না; এটি API key ছাড়া অ্যাক্সেসযোগ্য imagery service, যার নিজস্ব terms আছে। বিনামূল্যে/ওপেন লাইসেন্সের বৈশ্বিক satellite imagery সাধারণত নির্ভরযোগ্যভাবে high-resolution basemap হিসেবে পাওয়া যায় না।

## Build
1. Android Studio-তে এই folder খুলুন।
2. Android SDK Platform 35 এবং JDK 17 ইনস্টল করুন।
3. Gradle sync সম্পন্ন করুন।
4. Build > Build APK(s) চালান।

## ফিচার
- Boundary ও LULC overlays আলাদাভাবে on/off
- Mouza নাম দিয়ে অনুসন্ধান
- সব সীমানায় zoom
- satellite / OSM streets / no basemap switch
- popup-এ Mouza নাম ও overlay নাম

## Data counts
- Boundary Placemark: 23
- LULC GroundOverlay: 22
