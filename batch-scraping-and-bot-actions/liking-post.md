# Liking Post

## Onlyfans Rate Limit

estimated to be around 1000 per day

## Self limit in program

Each like requests will have a delay&#x20;

Which will prevent the program from just spamming likes to the onlyfans server

| Time                                                                        | Delay                     |
| --------------------------------------------------------------------------- | ------------------------- |
| <p>Default <br></p>                                                         | Delay of 3 seconds        |
| if time divided by 50 has 0 remainder                                       | Set delay to 30 seconds   |
| if time divided by 60 is remainder is 0                                     | Return delay to 3 seconds |
| <p>If time divided by 60 has 0 remainder<br>and time divided by 50 is 0</p> | Set delay to 15 seconds   |



