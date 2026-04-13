# Head of AI — GH Pages Deployment

## Repo structure

```
your-repo/
├── index.html               ← login page (already done)
└── <SHA1_OF_PASSWORD>/
    └── index.html           ← the actual doc (already done)
```

## Steps

### 1. Choose your password and get its SHA1 hash

Run this in your terminal:

```bash
echo -n "yourpassword" | shasum
```

Or in Python:
```python
import hashlib
print(hashlib.sha1(b"yourpassword").hexdigest())
```

### 2. Rename the folder

Rename `HASH_FOLDER_GOES_HERE/` to the SHA1 hash you just generated.
Example: `a94a8fe5ccb19ba61c4c0873d391e987982fbbd3/`

### 3. Push to your repo

```
git add .
git commit -m "add head-of-ai doc"
git push
```

### 4. That's it

Your login page will be at:
  https://mot-displate.github.io/<repo-name>/

Visitors enter the password → the page hashes it → checks if the folder exists → redirects.

---
Note: This is the same SHA1 folder method used in brainwall and influcalc.
Security level: casual access only (not cryptographic). Good for internal docs.
