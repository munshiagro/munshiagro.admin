মুন্সী এগ্রো — পাবলিক ড্যাশবোর্ড ও লগইন প্ল্যাটফর্ম

এই প্যাকেজে যা আছে
- index.html: মূল পাবলিক পেজ। লগইন ছাড়া সারাংশ/চার্ট ও পাবলিক ফার্ম ম্যাপ দেখা যাবে; উপরে Admin, Staff, Investor Login থাকবে।
- dashboard.html: বিদ্যমান Firebase ও role-based ব্যবস্থাপনা ড্যাশবোর্ড। পাবলিক ভিউতে শুধু privacy-safe aggregate/relative-trend দেখায়; Admin/Staff/Investor লগইন হলে অনুমোদিত স্ক্রিন দেখায়।
- interactive_farm_map.html: একই ফার্ম ম্যাপ। index.html থেকে ?public=1 প্যারামিটারে খুললে এটি read-only দেখায়; সরাসরি খুললে স্থানীয় নোট-ফর্মের পুরোনো আচরণ থাকবে।

GitHub Pages-এ আপডেট
1. আগে রিপোজিটরির বর্তমান ফাইলগুলোর ব্যাকআপ রাখুন।
2. এই প্যাকেজের index.html, dashboard.html এবং interactive_farm_map.html ফাইল তিনটি রিপোজিটরির root folder-এ আপলোড করে পুরোনো ফাইল replace করুন।
3. style.css, script.js, logo/profile/cover ছবি, manifest এবং Firebase-সংক্রান্ত বাকি ফাইলগুলো ডিলিট করবেন না। index.html এখনও style.css ও script.js ব্যবহার করে।
4. Commit changes করে 1–3 মিনিট অপেক্ষা করুন। তারপর https://munshiagro.github.io/munshiagro.admin/index.html খুলে Ctrl+F5 চাপুন।
5. লগইন ছাড়া পাবলিক ড্যাশবোর্ড, পাবলিক চার্ট এবং read-only জমির নকশা দেখুন। তারপর Admin/Staff/Investor Login আলাদা করে পরীক্ষা করুন।

গুরুত্বপূর্ণ
- এই পরিবর্তন ফাইল তৈরি করে; এটি নিজে থেকে GitHub-এ প্রকাশ করে না।
- Firebase project/rules আগের মতো রাখা হয়েছে। লাইভে প্রকাশের পরে অবশ্যই অনুমতি ও লগইন পরীক্ষা করুন।
- পাবলিক সারাংশে মূল টাকার অঙ্ক, লেনদেনের নোট, বেতন, ফোন/NID বা বিনিয়োগকারীর ব্যক্তিগত তথ্য দেখানো হয় না।
- ফার্ম ম্যাপ ধারণাগত। 240 x 120 ফুট এবং 40 ফুটের ফাঁকা অংশ রাখা হয়েছে; বাস্তব জোনের মাপ এখনও জরিপ নকশা দিয়ে নিশ্চিত করতে হবে।
- অনিরাপদ পুরোনো fallback password কেবল Firebase disabled অবস্থায় কোডে থাকলে ব্যবস্থাপনাকে নিরাপদ ধরে নেবেন না। Firebase Authentication ও Firestore Rules-ই নিরাপত্তার মূল অংশ হওয়া উচিত।
