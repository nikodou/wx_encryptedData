# wx_encryptedData
java解析小程序加密数据解密算法


AES.java ---- AES加密

WxPKCS7Encoder.java 微信小程序加解密

WXCore.java  封装对外访问方法 



输入解析的小程序的 appId ，使用微信小程序授权获取的 sessionKey 值;

<button open-type="getPhoneNumber" bindgetphonenumber="getPhoneNumber">获取手机号码 </button>
Page({
  getPhoneNumber: function (e) {
    console.log(e.detail.errMsg)
    console.log(e.detail.iv)
    console.log(e.detail.encryptedData)
  }
})

从小程序的button按钮获取到 IV 和 encryptedData 数据传输到接口，调用解析即可获取到微信解密数据！


	public static void main(String[] args) throws Exception{
	   String appId = "wxxxxxxxxxxxxxx01";
	   String encryptedData =      "Zratztnh8F4yAQ3KBIG5tWEGgrcA3E/WGG4kMmdVo2s6T5ti1MlH/4XNzFxrprCZMzXy1TvTsNoWwOuElmiKydt9ipxc60ix9GlfoAKR2mRmpsIEKj2RvfynT3xHNyZ4cYugCHa/iGVVGosj0nHQJ4Agi3745hHYcNSoPw+ZPMqty4LV8X1goILnLIx1vZcBzZt34S+5MIie14hGQ79vtg==";
	   String sessionKey = "CkY36cHwxqKuzJy5VraTFQ==";
	   String iv = "k+lDDrGJkO0Nu2+ThPbhTQ==";
       System.out.println(decrypt(appId, encryptedData, sessionKey, iv));
    }
