let keystr = "XINGHUOLIAOYUAN7"; //密钥

// 字符串转hex
let string_to_hex = function (str) {
  let tempstr = "";
  for (let i = 0; i < str.length; i++) {
    if (tempstr === "") tempstr = str.charCodeAt(i).toString(16);
    else tempstr += str.charCodeAt(i).toString(16);
  }
  return tempstr;
};
let key = string_to_hex(keystr);
key = CryptoJS.enc.Hex.parse(key);

// 加密
const getEncryptedString = (src) => {
  const enc = CryptoJS.AES.encrypt(src, key, {
    mode: CryptoJS.mode.ECB,
    padding: CryptoJS.pad.Pkcs7
  });
  const enced = enc.ciphertext.toString();
  return enced;
};
// 解密
const getDecryptString = (enced) => {
  const dec = CryptoJS.AES.decrypt(CryptoJS.format.Hex.parse(enced), key, {
    mode: CryptoJS.mode.ECB,
    padding: CryptoJS.pad.Pkcs7
  });
  let decstr = CryptoJS.enc.Utf8.stringify(dec);
  return decstr;
};
window.getEncryptedString = getEncryptedString;
window.getDecryptString = getDecryptString;
