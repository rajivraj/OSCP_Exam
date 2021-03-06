# Online Password Cracking

* password security audits.
* Note that blindly running online brute force attack could violate a security policy and would automatically disable the service.
  * leaving the service in accessible until a administrator enables it.
  * we should be very careful and stealth.

## Brute Force Methodology

![](../../.gitbook/assets/image%20%28123%29.png)

![](../../.gitbook/assets/image%20%28124%29.png)

## Username Enumeration

* If the application, when a failed login occurs, if the application respond with reason for the failure \(Password is incorrect, or, Username is invalid\) then we could easily enumerate usernames.
* If there is password change / forgotten page, where it asks for username, then we could easily enumerate users there.
* If the application allows new users to register and specify their own usernames, username enumeration is virtually impossible to prevent if the application is to prevent duplicate usernames from being registered.
* it may still be possible to enumerate usernames based on the time taken for the application to respond to the login request. Applications often perform very different back-end processing on a login request, depending on whether it contains a valid username.

## Key to a successful online password cracking

Step 1 : Enumerate and verify all the possible username and verify them.

Step 2 : Find suspicious webpages on which we could run "cewl" tool to get a good and rich password list, instead of just randomly password list.

Step 3 : Create one more copy of the password list in reverse order, this is helpful in CTF, and other penetration testing exams. `tac pass.txt > rev_pass.txt.` 

Test "pass.txt" first for 5 minutes, if no success then test "rev\_pass.txt" for 5 minutes.

Step 4 :

1. Choosing your target
2. \(optional, if step 1 is unsuccessful then use this step\) Choose your user list
3. \(optional, if step 2 is unsuccessful then use this step\) Choose your "reverse password" / "password" list
4. Grep output of incorrect responses to differentiate between a successful login vs unsuccessful one. E.g. "incorrect" "error" used in 3rd parameter in hydra.

