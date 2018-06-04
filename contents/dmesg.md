# Dmesg

Dmesg is a system utility to interact with the Kernel ring buffer

## Common options

| long		| short | description 								|
-----------------------------------------------------------------
| --clear  	| -C	| Clear the buffer 							|
| --file   	| -F    | Output to a file instead of buffer 		|
| --humaan 	| -H    | Make the output humanly readable 			|
| --level  	| -l    | Filter messeges my level 					|
| --follow 	| -w	| Don't exit and listen to new messages 	|
| --syslog 	| -S	| Use syslog instead of kernel ring buffer 	|


## Log levels

| level  | description 						|
---------------------------------------------
| crit 	 | critical conditions				|
| err 	 | error conditions					|
| warn 	 | warning conditions				|
| notice | normal but significant condition |
| info 	 | informational					|
| debug  | debug-level messages				|

