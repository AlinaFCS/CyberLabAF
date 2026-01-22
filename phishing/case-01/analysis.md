This lab was completed by me on the TryHackMe platform. The lab included a series of questions that needed to be answered. In the first screenshot, the task itself is shown. In the second screenshot, I present the questions that were asked and then demonstrate how I found the answers to those questions.


<img width="869" height="528" alt="image" src="https://github.com/user-attachments/assets/f4809813-d1e8-46c6-94f5-0dfe42c2d533" />

<img width="885" height="693" alt="image" src="https://github.com/user-attachments/assets/0cbfd1b4-1e3a-4422-be9e-fd43362d47c0" />

Next, I switched to the virtual machine and opened the specified file there using Thunderbird.

<img width="962" height="796" alt="image" src="https://github.com/user-attachments/assets/f2005d60-d527-4004-8ebc-311bbb2eabf5" />
All the required information, including the transfer reference number, the sender of the email, the email address, the reply-to email address, and the originating IP address, was found in the email header and the email body.

<img width="969" height="866" alt="image" src="https://github.com/user-attachments/assets/438585dc-b29a-4985-8e3f-43442fb1f556" />


Next, in order to answer the question about who the original IP belongs to, I went to a website called whois.com, entered the IP address there, and it returned all the necessary information.
<img width="876" height="255" alt="image" src="https://github.com/user-attachments/assets/3a958ecb-723f-4e46-85e8-e9cf762170b2" />

<img width="992" height="818" alt="image" src="https://github.com/user-attachments/assets/2f0537f9-351d-4225-858e-298e1b12ede0" />

Next, there was a question about the SPF record for the Return-Path domain and the DMARC record for the Return-Path domain. To find this information, I went to mxtoolbox.com and submitted the corresponding queries.

<img width="858" height="249" alt="image" src="https://github.com/user-attachments/assets/2c431afe-02f2-4aab-a1d7-560b9f105a47" />

<img width="826" height="241" alt="image" src="https://github.com/user-attachments/assets/afeb99ba-136c-42d7-8149-d6d946667f37" />
<img width="813" height="299" alt="image" src="https://github.com/user-attachments/assets/8e4187cc-5154-4b14-8f2b-b88e8786f36d" />

To answer the last four questions, I saved the file attached to the email on the desktop. Then, using the terminal, I generated the file’s hash, and after obtaining the hash, I went to the VirusTotal website and retrieved all the necessary information.


<img width="865" height="521" alt="image" src="https://github.com/user-attachments/assets/ec81604f-89a5-4594-b8e6-c3878129eb23" />

<img width="942" height="76" alt="image" src="https://github.com/user-attachments/assets/9b5d928b-05d9-4cdb-85d7-4ec9392e544c" />

<img width="1774" height="764" alt="image" src="https://github.com/user-attachments/assets/039a8ce5-e053-44f5-8455-1f045c971330" />








