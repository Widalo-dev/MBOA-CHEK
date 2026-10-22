# MBOA-CHEK
Application Anti-arnarque mobile Money pour le Cameroun 🇨🇲 async function deriveKey(passWord,salt) {
  let enc = new TextEncoder().encode(passWord);
  let byte = new TextEncoder().encode(salt);
let keyMaterial = await crypto.subtle.importKey("raw",enc,"PBKDF2",false,["deriveBits"]);
  let vraiKey = await crypto.subtle.deriveBits({
    name:"PBKDF2",
    salt:byte,
  iterations:100000,
  hash:"SHA-256",
  },
keyMaterial,
  256
);
return vraiKey;
}
(async () => {
let x = await deriveKey("1234","monsel123");
console.log("Taille",x.byteLength);
  let vue = new Uint8Array(x);
  console.log(vue);
  })();
