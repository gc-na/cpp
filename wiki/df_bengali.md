# [লিনাক্স] C Shell (csh) df ব্যবহার: ডিস্ক স্পেসের তথ্য দেখানো

## Overview
`df` কমান্ডটি ডিস্কের ব্যবহৃত এবং উপলব্ধ স্পেসের তথ্য প্রদর্শন করে। এটি সিস্টেমের বিভিন্ন ফাইল সিস্টেমের জন্য ডিস্ক স্পেসের অবস্থা সম্পর্কে ধারণা দেয়।

## Usage
`df` কমান্ডের মৌলিক সিনট্যাক্স হল:

```
df [options] [arguments]
```

## Common Options
- `-h`: মানব-পঠনযোগ্য ফরম্যাটে আউটপুট দেখায় (যেমন KB, MB, GB)।
- `-T`: ফাইল সিস্টেমের টাইপ প্রদর্শন করে।
- `-a`: সমস্ত ফাইল সিস্টেম, এমনকি মাউন্ট করা না হওয়া ফাইল সিস্টেমও দেখায়।

## Common Examples
- সমস্ত ফাইল সিস্টেমের ডিস্ক স্পেস দেখানোর জন্য:
  ```bash
  df
  ```

- মানব-পঠনযোগ্য ফরম্যাটে ডিস্ক স্পেস দেখানোর জন্য:
  ```bash
  df -h
  ```

- ফাইল সিস্টেমের টাইপ সহ ডিস্ক স্পেস দেখানোর জন্য:
  ```bash
  df -T
  ```

- সমস্ত ফাইল সিস্টেম, মাউন্ট করা না হওয়া ফাইল সিস্টেম সহ দেখানোর জন্য:
  ```bash
  df -a
  ```

## Tips
- `df -h` ব্যবহার করা সর্বদা ভালো, কারণ এটি ডিস্ক স্পেসের তথ্যকে আরও সহজে পড়ার যোগ্য করে তোলে।
- নিয়মিতভাবে `df` চালিয়ে আপনার সিস্টেমের ডিস্ক স্পেসের অবস্থা পর্যবেক্ষণ করুন, যাতে আপনি অপ্রয়োজনীয় ফাইল মুছে ফেলার সময় নির্ধারণ করতে পারেন।