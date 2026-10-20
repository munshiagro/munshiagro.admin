মুন্সী এগ্রো — পণ্যের ছবি আপলোড সমস্যা সমাধান

প্যাকেজের ফাইল:
- index.html — পাবলিক দোকান; হোস্ট করা ছবি ও ছোট কমপ্রেস করা ছবি উভয়ই দেখাতে পারবে।
- dashboard.html — Admin-এর পণ্য যোগ/ছবি পরিবর্তন/সংরক্ষণ ব্যবস্থা।

কী ঠিক করা হয়েছে:
1. নতুন পণ্য যোগ করার সময় সরাসরি ছবি ফাইল নির্বাচন করা যায়; নির্বাচন করলে ফাইলের নাম ও প্রিভিউ দেখা যায়।
2. বিদ্যমান পণ্যের জন্য লুকানো ফাইল ইনপুটের বদলে দৃশ্যমান ফাইল সিলেক্টর আছে; নির্বাচন করার পর নির্দিষ্ট পণ্যের “সংরক্ষণ” চাপতে হবে।
3. ফাইলের ধরন (JPG/PNG/WebP) ও সর্বোচ্চ ৫ MB যাচাই করা হয়।
4. Firebase Storage কাজ করলে ছবিটি Storage-এ আপলোড হয় এবং download URL-টি পণ্যে যুক্ত হয়।
5. Storage অনুপলব্ধ হলে ব্রাউজারে ছবিটি WebP/JPEG-এ কমপ্রেস করে Firestore shared data-তে imageData হিসেবে রাখা হয়—কেবল shared document-এর আনুমানিক JSON 900 KiB-এর নিচে থাকলে। এতে Firestore-এর 1 MiB সীমার জন্য কিছু জায়গা রাখা হয়।
6. Storage fallback-ও সম্ভব না হলে স্পষ্ট ত্রুটি দেখায়; সফল না হলে “সফল” বলে না।
7. Public product catalogue imageData-ও চিনবে এবং fallback ছবি দেখাবে।
8. পণ্যের ডেটা পরিবর্তনের সময় এখন Firestore save-এর ফলাফল অপেক্ষা করা হয়, যাতে failure হলে সফলতার বার্তা না আসে।

GitHub-এ আপডেট:
1. বর্তমান index.html ও dashboard.html ব্যাকআপ নিন।
2. এই ZIP-এর index.html এবং dashboard.html দিয়ে রিপোজিটরির মূল ফোল্ডারে পুরনো ফাইল Replace করুন।
3. অন্য CSS, JS, ছবি, Firebase configuration বা interactive_farm_map.html মুছবেন না।
4. Commit changes করে সাইটে Ctrl+F5 দিন।
5. Admin Login > পণ্য ব্যবস্থাপনা খুলুন। নতুন পণ্যে ছবি নির্বাচন করে “পণ্য যোগ করুন”; বিদ্যমান পণ্যে ছবি নির্বাচন করে ওই সারির “সংরক্ষণ” চাপুন।

নোট:
- আসল ও বড় পণ্যের ছবির জন্য Firebase Storage সক্রিয় করা উত্তম। Firebase Console > Storage-এ bucket সেটআপ এবং যথাযথ authenticated-admin Security Rules প্রয়োজন।
- Firestore fallback সীমিত; shared data বড় হলে fallback প্রত্যাখ্যান করবে এবং Storage চালু করতে বলবে।
- Firebase Storage-এর নিয়ম এমন রাখবেন যাতে শুধুমাত্র অনুমোদিত Admin ছবি আপলোড/পরিবর্তন করতে পারে। পাবলিক ক্রেতাকে upload permission দেবেন না।
- এই প্যাকেজে GitHub বা Firebase Console-এর পরিবর্তন নিজে থেকে প্রকাশ করা হয়নি।
