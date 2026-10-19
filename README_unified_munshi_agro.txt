মুন্সী এগ্রো — একীভূত ওয়েবসাইট আপডেট

এই প্যাকেজে আছে:
1. index.html — মূল ওয়েবসাইট; উপরে Admin, Staff ও Investor Login আছে। আলাদা ফার্ম-ম্যাপ পরিচিতি কার্ড বাদ দেওয়া হয়েছে; ম্যাপটি নিচের নিজস্ব সেকশনে আছে।
2. dashboard.html — আগের Firebase/লগইন/ডেটা ব্যবস্থার ওপর ভিত্তি করে ব্যবস্থাপনা ড্যাশবোর্ড।
3. interactive_farm_map.html — ক্লিকযোগ্য ফার্ম ম্যাপ।

GitHub Pages-এ আপলোড করার নিয়ম:
1. ZIP Extract করুন।
2. এই তিনটি HTML ফাইল আপনার `munshiagro.admin` রিপোজিটরির মূল ফোল্ডারে আপলোড করুন।
3. `index.html`-কে নতুন ফাইল দিয়ে Replace করুন। `dashboard.html` নামে নতুন ফাইল যোগ করুন। `interactive_farm_map.html`-কে Replace/আপডেট করুন, যদি প্যাকেজের সংস্করণ ব্যবহার করতে চান।
4. `style.css`, `script.js`, ছবি, logo, Firebase configuration এবং অন্য বিদ্যমান ফাইল মুছবেন না।
5. GitHub Pages শেষ হলে https://munshiagro.github.io/munshiagro.admin/ খুলে Ctrl+F5 চাপুন।

গুরুত্বপূর্ণ:
- Firebase config, login handlers, cloud document এবং DATA schema পুরোনো ড্যাশবোর্ড থেকেই রাখা হয়েছে; নতুন index থেকে role-specific login অপশন পুরোনো লগইন বাটনে ট্রিগার করে।
- `dashboard.html` ফাইলটি একই রিপোজিটরিতে থাকতে হবে, কারণ index এটি embed করে।
- পুরোনো `munshi_agro_tracker.html` এখনই মুছবেন না। নতুন সংস্করণ পরীক্ষা করে নিশ্চিত হওয়ার পর প্রয়োজন হলে মুছুন। মূল index থেকে পুরোনো Tracker লিংক ও নাম সরানো হয়েছে।
- ফার্ম ম্যাপের নোট এখনো localStorage-এ সংরক্ষিত হয়; এটি Firebase-এ সিঙ্ক করে না।
- ফাইল আপলোডের আগে চাইলে বর্তমান `index.html` ও অন্য ফাইলের backup রাখুন।
