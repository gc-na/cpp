# [লিনাক্স] C Shell (csh) sha512sum ব্যবহার: ফাইলের SHA-512 হ্যাশ তৈরি করা

## Overview
`sha512sum` কমান্ডটি ফাইলের SHA-512 হ্যাশ তৈরি করে। এটি সাধারণত ফাইলের অখণ্ডতা যাচাই করার জন্য ব্যবহৃত হয়, যাতে নিশ্চিত হওয়া যায় যে ফাইলটি পরিবর্তিত হয়নি।

## Usage
বেসিক সিনট্যাক্স হল:

```csh
sha512sum [options] [arguments]
```

## Common Options
- `-b` : বাইনারি ফাইলের জন্য হ্যাশ গণনা করে।
- `-c` : একটি হ্যাশ ফাইল পরীক্ষা করে।
- `-h` : সাহায্য তথ্য দেখায়।
- `-t` : টেক্সট ফাইলের জন্য হ্যাশ গণনা করে।

## Common Examples
1. একটি ফাইলের SHA-512 হ্যাশ তৈরি করা:
   ```csh
   sha512sum example.txt
   ```

2. একটি হ্যাশ ফাইল তৈরি করা:
   ```csh
   sha512sum example.txt > example.txt.sha512
   ```

3. একটি হ্যাশ ফাইল যাচাই করা:
   ```csh
   sha512sum -c example.txt.sha512
   ```

4. বাইনারি ফাইলের জন্য হ্যাশ গণনা করা:
   ```csh
   sha512sum -b example.bin
   ```

## Tips
- নিশ্চিত করুন যে আপনি হ্যাশ ফাইলটি সঠিকভাবে তৈরি করেছেন এবং যাচাই করার সময় সঠিক ফাইলের সাথে তুলনা করছেন।
- হ্যাশ ফাইলগুলি নিরাপদ স্থানে সংরক্ষণ করুন, যাতে ভবিষ্যতে ফাইলের অখণ্ডতা যাচাই করতে পারেন।
- বড় ফাইলের জন্য হ্যাশ গণনা করতে সময় লাগতে পারে, তাই ধৈর্য ধরুন।