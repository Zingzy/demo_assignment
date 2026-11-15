# Login System Test Cases

| Test Case ID | Test Scenario | Input Data | Expected Output |
|---|---|---|---|
| TC_01 | Successful login with valid credentials | Username = `user1`; Password = `pass123`; click Login | User is authenticated and the application displays **“Login successful.”** |
| TC_02 | Username is empty | Username = empty; Password = `pass123`; click Login | Login is not submitted. The form displays **“Username is required.”** |
| TC_03 | Password is empty | Username = `user1`; Password = empty; click Login | Login is not submitted. The form displays **“Password is required.”** |
| TC_04 | Password is shorter than 6 characters | Username = `user1`; Password = `abc12` (5 characters); click Login | Login is not submitted. The form displays **“Password must be at least 6 characters.”** |
| TC_05 | Password is exactly 6 characters | Username = `user1`; Password = `abc123` (6 characters); click Login | Password length validation passes. With valid credentials, the application displays **“Login successful.”** |
| TC_06 | Username and password do not match a valid account | Username = `user1`; Password = `wrong99`; click Login | Login is denied. The application displays **“Invalid username or password.”** and counts one failed attempt. |
| TC_07 | Three consecutive failed login attempts | Submit incorrect credentials three times for the same account | After the third failed attempt, login is denied and the application displays **“Account locked after 3 failed login attempts.”** |
| TC_08 | Correct credentials submitted after the account is locked | Account was locked after TC_07; Username = `user1`; Password = `pass123`; click Login | Login remains denied. The application displays **“Account is locked. Contact support to unlock it.”** |
