মুন্সী এগ্রো — ওয়েবসাইট আপডেট প্যাকেজ

প্যাকেজে আছে:
- index.html: গাঢ় সবুজ ডিজাইন, বড় প্রোডাক্ট ভিজুয়াল, GitHub product-images থেকে স্বয়ংক্রিয় ছবি লোড।
- dashboard.html: PDF একই স্ক্রিনে modal viewer-এ দেখানো, modal layering ও গাঢ় সবুজ theme উন্নয়ন।
- project-plan.pdf এবং invest-plan.pdf: ড্যাশবোর্ডের fallback PDF ফাইল।
- product-images/README.txt: পণ্যের ছবি ফাইলের নামের নিয়ম।

GitHub-এ করার নিয়ম:
1) আগে বর্তমান index.html ও dashboard.html backup রাখুন।
2) এই প্যাকেজের index.html, dashboard.html, project-plan.pdf, invest-plan.pdf repository root-এ একই নাম দিয়ে upload/replace করুন।
3) product-images নামে folder তৈরি/ব্যবহার করুন এবং README.txt সহ আপনার JPG ছবিগুলো রাখুন।
4) Commit changes করুন। GitHub Pages update হতে কয়েক মিনিট লাগতে পারে।
5) মোবাইলে browser cache এড়াতে পেজ বন্ধ করে আবার খুলুন বা hard refresh করুন।

ছবির নাম: পণ্যের ID + .jpg। উদাহরণ: rui.jpg, calf.jpg, goat-kid.jpg।
বর্তমানে পণ্যের ID-এর জন্য JPG path অটো খোঁজা হয়। অন্য extension ব্যবহার করলে index.html-এর repoImage path বদলাতে হবে।
একই নাম দিয়ে ছবি replace করলে সাধারণত update হবে; browser/CDN cache থাকলে কিছুক্ষণ পুরোনো ছবি থাকতে পারে।

গুরুত্বপূর্ণ সীমাবদ্ধতা:
- GitHub Pages static hosting; Admin Panel থেকে সরাসরি GitHub-এ ছবি upload/commit করার স্বয়ংক্রিয় API এই প্যাকেজে নেই। ছবি বদলাতে repository-তে নিজে upload/commit করতে হবে।
- পাবলিক দোকানের পণ্যের ছবি এখন repository-র product-images/{product-id}.jpg থেকে লোড হবে; Firebase-এর পুরোনো imageUrl/imageData storefront image হিসেবে অগ্রাধিকার পাবে না। Admin Panel-এর Firebase image update তাই public product photo বদলাবে না—ছবি বদলাতে একই নামের JPG repository-তে replace/commit করতে হবে।
- PDF modal, CSS এবং inline JavaScript source-level এডিট করা হয়েছে; লাইভ Firebase ও ব্রাউজারে end-to-end পরীক্ষা করা হয়নি।
- এই প্যাকেজে Firestore data structure, login credentials, Firebase rules বা order records পরিবর্তন করা হয়নি।
