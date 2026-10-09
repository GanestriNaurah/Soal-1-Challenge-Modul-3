# Soal-1-Challenge-Modul-3

## Step 1
Buat folder di terminal VS Code
```bash
mkdir audit-ts
cd audit-ts
npm init -y
npm install typescript @types/node --save-dev
npx tsc --init
mkdir src
```

## Step 2
Pastikan strict pada tsconfig.json di dalam folder audit-ts sudah bernilai true.

## Step 3
Lalu, buat new file di dalam folder src dengan nama file audit.ts dan buat dalam file tersebut dengan code
```bash
function doubleNumber(value: any): number {
return value * 2;
}

console.log(doubleNumber(10));
console.log(doubleNumber("halo"));
```
Jangan lupa buat ctrl + S.

## Step 4
Cek dengan command `npx tsx src/audit.tsx`, akan keluar hasil 20 NaN.

## Step 5
Edit isi file dengan tambahan error message seperti ini.
```bash
function doubleNumber(value: number|string): number {
    if (typeof value !== "number") {
        throw new Error("Input harus berupa angka");
    }
    return value * 2;
}

console.log(doubleNumber(10));
try {
    console.log(doubleNumber("halo"));
} catch (error) {
    console.log((error as Error).message);
}
```

## Step 6
Cek dengan command `npx tsx src/audit.tsx`, akan keluar hasil 20 Input harus berupa angka. Untuk memastikan tidak ada error, cek dengan command `npx tsc --noEmit`. Kalau kosong berarti aman.
