# OpenSSL 实现 RSA 非对称加密

```shell
# 生成私钥
openssl genrsa -out private.pem

# 从私钥中提取出公钥
openssl rsa -in private.pem -pubout -out public.pem

# 查看秘钥信息
openssl asn1parse -i -in private.pem > private.txt

OFFSET=$(openssl asn1parse -i -in public.pem | grep "BIT STRING " | awk -F ":" '{print $1}' | awk '$1=$1')

openssl asn1parse -i -in public.pem -strparse "${OFFSET}" > public.txt

# 原始文件
cat > hello.txt << EOF
Hello World！
EOF

# 加密文件
openssl rsautl -encrypt -in hello.txt -inkey public.pem -pubin -out hello.en

# 解密文件
openssl rsautl -decrypt -in hello.en -inkey private.pem -out hello.de
```