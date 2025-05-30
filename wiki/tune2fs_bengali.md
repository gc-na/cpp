# [লিনাক্স] C Shell (csh) tune2fs ব্যবহার: ফাইল সিস্টেমের বৈশিষ্ট্য পরিবর্তন

## Overview
`tune2fs` কমান্ডটি Linux ফাইল সিস্টেমের বৈশিষ্ট্য পরিবর্তন করতে ব্যবহৃত হয়। এটি ext2, ext3 এবং ext4 ফাইল সিস্টেমের জন্য বিভিন্ন সেটিংস কনফিগার করার সুযোগ দেয়, যেমন জার্নালিং, ব্লক সংখ্যা, এবং অন্যান্য অপশন।

## Usage
`tune2fs` কমান্ডের মৌলিক সিনট্যাক্স হল:

```bash
tune2fs [options] [arguments]
```

## Common Options
- `-c <mount-count>`: সর্বাধিক মাউন্ট সংখ্যা সেট করে।
- `-i <interval>`: ফাইল সিস্টেমের জন্য ইন্টারভ্যাল সেট করে।
- `-j`: জার্নালিং সক্ষম করে।
- `-O <feature>`: নির্দিষ্ট বৈশিষ্ট্য সক্রিয় করে।
- `-L <label>`: ফাইল সিস্টেমের লেবেল সেট করে।

## Common Examples
1. **জার্নালিং সক্ষম করা:**
   ```bash
   tune2fs -j /dev/sda1
   ```

2. **মাউন্ট সংখ্যা সেট করা:**
   ```bash
   tune2fs -c 20 /dev/sda1
   ```

3. **ফাইল সিস্টেমের বৈশিষ্ট্য সক্রিয় করা:**
   ```bash
   tune2fs -O dir_index /dev/sda1
   ```

4. **ফাইল সিস্টেমের লেবেল পরিবর্তন করা:**
   ```bash
   tune2fs -L mylabel /dev/sda1
   ```

## Tips
- ফাইল সিস্টেমের পরিবর্তন করার আগে সবসময় ব্যাকআপ নিন।
- `tune2fs` ব্যবহার করার সময় সতর্ক থাকুন, কারণ ভুল সেটিংস ফাইল সিস্টেমের অকার্যকর হতে পারে।
- ফাইল সিস্টেমের বর্তমান অবস্থা পরীক্ষা করতে `dumpe2fs` কমান্ড ব্যবহার করুন।