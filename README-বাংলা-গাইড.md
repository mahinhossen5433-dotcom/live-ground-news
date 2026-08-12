# The Live Ground — সেটআপ গাইড (ধাপে ধাপে)

তোমার সাইট বানানো শেষ। এখন এটা লাইভ করতে ও অ্যাডমিন প্যানেল অ্যাক্টিভ করতে নিচের ধাপগুলো ফলো করো। প্রথমবার সেটআপ করতে ১৫-২০ মিনিট লাগবে, এরপর থেকে শুধু `/admin` এ গিয়ে নিউজ লিখলেই হবে।

---

## ধাপ ১: GitHub এ কোড আপলোড করো

1. https://github.com এ গিয়ে ফ্রি অ্যাকাউন্ট বানাও (না থাকলে)
2. উপরে ডানদিকে **+** বাটনে ক্লিক করে **New repository** সিলেক্ট করো
3. নাম দাও: `the-live-ground` (Public বা Private, দুটোই চলবে) → **Create repository**
4. রিপো খোলার পর **"uploading an existing file"** লিংকে ক্লিক করো
5. এই ZIP ফাইলটা এক্সট্র্যাক্ট করে ভেতরের **সব ফাইল ও ফোল্ডার** (src, admin, package.json, netlify.toml, .eleventy.js, .gitignore — সবকিছু) সিলেক্ট করে GitHub এর আপলোড বক্সে ড্র্যাগ করে ছাড়ো
6. নিচে **Commit changes** বাটনে ক্লিক করো

> ⚠️ `node_modules` ও `_site` ফোল্ডার ZIP এ নেই — এগুলোর দরকার নেই, Netlify নিজেই বানিয়ে নেবে।

---

## ধাপ ২: Netlify এ সাইট কানেক্ট করো

1. https://netlify.com এ লগইন করো (GitHub দিয়েই লগইন করতে পারবা)
2. **Add new site → Import an existing project** সিলেক্ট করো
3. **GitHub** সিলেক্ট করে `the-live-ground` রিপো বেছে নাও
4. Build সেটিংস অটোমেটিক আসবে (netlify.toml থেকে), তারপরও চেক করে নাও:
   - **Build command:** `npm run build`
   - **Publish directory:** `_site`
5. **Deploy site** ক্লিক করো — ২-৩ মিনিটে সাইট লাইভ হয়ে যাবে

---

## ধাপ ৩: অ্যাডমিন প্যানেল (লগইন সিস্টেম) চালু করো

1. Netlify ড্যাশবোর্ডে তোমার সাইটে ঢুকে **Site configuration → Identity** এ যাও → **Enable Identity**
2. Identity সেটিংসে **Registration** এ যাও → **Invite only** সিলেক্ট করো (এতে শুধু তুমি আর যাকে ইনভাইট করবা সেই লগইন করতে পারবে)
3. এবার **Services** সেকশনে যাও → **Git Gateway** এ **Enable Git Gateway** ক্লিক করো
4. **Identity** ট্যাবে ফিরে গিয়ে **Invite users** ক্লিক করো → তোমার নিজের ইমেইল দাও
5. তোমার ইমেইলে একটা ইনভাইট লিংক আসবে → ক্লিক করে পাসওয়ার্ড সেট করো

---

## ধাপ ৪: নিউজ লেখা শুরু করো

তোমার সাইটের লিংকের সাথে `/admin` যোগ করে ভিজিট করো, যেমন:
`https://your-site-name.netlify.app/admin`

লগইন করে **"News Articles" → "New Article"** ক্লিক করো। যা যা ফিল করবে:
- **Headline** — বোল্ড হেডলাইন (কার্ডে/টপে এমনিতেই বোল্ড দেখাবে)
- **Category** — Cricket, Football, Live Updates, Transfer News, Match Preview
- **Short summary** — হেডলাইনের নিচে normal লেখা যেটা দেখা যাবে
- **Cover image** — ছবি আপলোড করো (ড্র্যাগ-ড্রপ করা যাবে মোবাইল থেকেও)
- **Feature on homepage top banner** — অন করলে এই নিউজটা সবার উপরে বড় করে দেখাবে
- **Full article** — পুরো নিউজ লিখো

**Publish** চাপলেই সাথে সাথে (১-২ মিনিটে) সাইটে লাইভ হয়ে যাবে।

---

## সাইটের স্ট্রাকচার (ভবিষ্যতে বুঝতে সুবিধা হবে)

- `src/articles/` → প্রতিটা নিউজ একটা করে ফাইল (অ্যাডমিন থেকে অটো তৈরি হয়)
- `src/_includes/` → হেডার, ফুটার, কার্ড, লেআউট টেমপ্লেট
- `src/css/style.css` → পুরো ডিজাইন (রং, ফন্ট ইত্যাদি)
- `src/_data/site.json` → সাইটের নাম, ক্যাটাগরি লিস্ট (এখানে ইউআরএল আপডেট করতে ভুলো না, ধাপ ২ এর পর তোমার আসল Netlify লিংক বসিয়ে দিও)
- `admin/config.yml` → অ্যাডমিন প্যানেলের ফিল্ড/সেটিংস কনফিগারেশন

কোনো ধাপে আটকে গেলে স্ক্রিনশট দিয়ে জানাও, আমি হেল্প করব।
