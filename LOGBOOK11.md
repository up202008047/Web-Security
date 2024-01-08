 

## **Task 1**

- Ownership of a public key certificate is based on the integrity and identification provided by the both parties.
- The main focus is to make the website private by using public key certificates through trusted entities such as Certificate Authority. 

- To achieve that we first need to copy the OpenSSL configuration file into our Labsetup folder and create necessary subdirectories and files.

![](docs/pki1_1.png)

- Generated self-signed certificate in a way that we don't get prompted for additional information

![](docs/pki1_2.png)

- Using the commands given we were able to answer the following questions:

1. What part of the certificate indicates this is a CA’s certificate?

![](docs/pki1_q1.png)

2. What part of the certificate indicates this is a self-signed certificate?

![](docs/pki1_q2.png)
	
3. In the RSA algorithm, we have a public exponent, a private exponent d, a modulus n, and two secret numbers p and q, such that n=pq. Please identify the values for these elements in your certificate and key files.
	
	-modulus(n)	
![](docs/pki1_q31.png)
	-public exponent(publicExponent)
![](docs/pki1_q5.png)
	-privateExponent(d)
![](docs/pki1_q32.png)
	-prime1(p)
![](docs/pki1_q33.png)
	-prime2(q)
![](docs/pki1_q34.png)


---

## **Task 2**

- We used the following to generate a request using the new server key
- The -addext flag connects to different urls, that are pointing to the same web server

![](docs/pki2.png)

## **Task 3**

- First we uncommented the copy_extensions line in the openssl.cnf file

![](docs/pki3_1.png)

- Then run the command to create the certificate

![](docs/pki3_2.png)

- Using the give command we can see the alternative names

![](docs/pki3_3.png)

## **Task 4**

- To setup the website we copied the server.ctr and server.key files that we generated to the Labsetup/image_www/certs directory

![](docs/pki4_1.png)

- We modified the bank32_apache_ssl.conf file

![](docs/pki4_2.png)

- Inside do Docker container we started the Apache server and accessed the website http://www.bank32.com which gave us a warning

![](docs/pki4.png)

- Firefox did not connect to the website because it doesn't know the issuer of the website's certificate and therefore cannot trust it (error code SEC_ERROR_UNKNOWN_ISSUER). 
- When clicking View Certificate, we can check that the certificate we generated is being used

![](docs/pki4_5.png)

- To solve that we can go into the browser settings and import the .crt file to the trusted authorites

## **Task 5**

- We added www.youtube.com to the /etc/hosts/ file
- Visiting the website the browser displayed the following warning 

![](docs/pki5.png)

- This happened because the certificate that we are using to sign www.youtube.com was emitted for www.bank32.com.

- If we ignore the warning and accept the risk we get access to the clone of www.youtube.com

![](docs/pki5_2.png)

## **Task 6**

-We generated a new certificate request to the Youtube address and turn the certificate signing request into a X509 certificate

![](docs/pki6.png)

- We changed the Dockerfile so that it inlcudes the youtube.crt and youtube.key

- The website now appears as secure.





	
