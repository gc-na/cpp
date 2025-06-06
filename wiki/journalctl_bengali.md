# [লিনাক্স] C Shell (csh) journalctl ব্যবহার: সিস্টেম লগ দেখার জন্য একটি কমান্ড

## Overview
`journalctl` কমান্ডটি লিনাক্স সিস্টেমে লগ ফাইলগুলো দেখতে ব্যবহৃত হয়। এটি systemd এর লগিং সিস্টেমের অংশ এবং সিস্টেমের বিভিন্ন কার্যকলাপ এবং ত্রুটির তথ্য সংগ্রহ করে।

## Usage
`journalctl` কমান্ডের মৌলিক সিনট্যাক্স হলো:

```
journalctl [options] [arguments]
```

## Common Options
- `-b` : বর্তমান বুটের লগ দেখায়।
- `-f` : লগ ফাইলের শেষের দিকে রিয়েল-টাইম আপডেট দেখায়।
- `--since` : নির্দিষ্ট সময় থেকে লগ দেখানোর জন্য।
- `--until` : নির্দিষ্ট সময় পর্যন্ত লগ দেখানোর জন্য।
- `-u` : নির্দিষ্ট ইউনিটের লগ দেখায়।

## Common Examples
- বর্তমান বুটের লগ দেখতে:
  ```bash
  journalctl -b
  ```

- রিয়েল-টাইম লগ দেখতে:
  ```bash
  journalctl -f
  ```

- গতকাল থেকে লগ দেখতে:
  ```bash
  journalctl --since "yesterday"
  ```

- নির্দিষ্ট সার্ভিসের লগ দেখতে (যেমন `ssh.service`):
  ```bash
  journalctl -u ssh.service
  ```

## Tips
- লগ ফাইলগুলো বিশ্লেষণ করতে `grep` ব্যবহার করতে পারেন। উদাহরণস্বরূপ:
  ```bash
  journalctl | grep "error"
  ```

- লগগুলোকে পেজিংয়ের মাধ্যমে দেখতে `less` ব্যবহার করতে পারেন:
  ```bash
  journalctl | less
  ```

- নির্দিষ্ট সময়ের মধ্যে লগগুলো দেখতে `--since` এবং `--until` অপশন ব্যবহার করুন।