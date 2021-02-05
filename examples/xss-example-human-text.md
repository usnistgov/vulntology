# Human readable text based on XSS-Example.png

This displays how human readable descriptions can be derived from a vulntological representation of a vulnerability. <br />

Legend:<br />
**Object**<br />
[**Object Instantiation**]<br />
*Property*<br />
[*Value*]<br />

---

There is a **vulnerability**, *known as* [*CVE-2050-1234*]. It is of importance to the [*Industrial Control System*] and [*Health Care*] *sectors*.<br />
The **vulnerability** is due to code that originates from [*Acme Acmeproduct 1.0.0.*] <br />
The **vulnerability** [*CVE-2050-1234*] has [**one**] **scenario** that is an [*internet*] based [*cross-site scripting*]. <br />
The [**first**] **scenario** is *evidenced by* [*www.acme.com*]<br />
The [**first**] **scenario** *affects product* [*Acme Acmeproduct 1.0.0.*] <br />
The [**first**] **scenario** is *blocked by* **social engineering** of an [*application*] [*user*] via a [*malicious link*] and requiring [*user*] [*application*] **privileges**. <br />
The [**first**] **action** of the [**first**] **scenario** is [*code execution*] to the [*webserver*] which is the [*primary authorization scope*].<br />
The [**first**] **impact** of the [**first**] **action** is a [*low*] *criticality*, [*limited*] *scope*, [*direct write*].<br />
The [**second**] **action** of the [**first**] **scenario** is [*code execution*] to the [*browser*] which is the [*secondary authorization scope*].<br />
The [**first**] **impact** of the [**second**] **action** is a [*low*] *criticality*, [*limited*] *scope*, [*direct write*].<br />
The [**second**] **impact** of the [**second**] **action** is a [*low*] *criticality*, [*limited*] *scope*, [*direct read*]. <br />

---

![XSS-Example](xss-example.png "XSS-Example")