# grep-tail-head-and-nl-Challenge
Linux Basics for Hackers: Getting Started with Networking, Scripting, and Security in Kali

Let's say you want to display the five lines immediately beforealine that says # Step #6:
Configure output plugins using at least four of the commands you just learned.How would you
do it?(Hint:there are many more options to these commands than those we've discussed.
You can learn more commands by using the built-in Linux command man.For example,man
tail will show the help file for the tail command.)

nl -b a /etc/snort/snort.conf | grep output  
output :
  34  #  6) Configure output plugins
   529  # Step #6: Configure output plugins
   535  # output unified2: filename merged.log, limit 128, nostamp, mpls_event_types, vlan_event_types
   536  output unified2: filename snort.log, limit 128, nostamp, mpls_event_types, vlan_event_types
   539  # output alert_unified2: filename snort.alert, limit 128, nostamp
   540  # output log_unified2: filename snort.log, limit 128, nostamp 
   543  # output alert_syslog: LOG_AUTH LOG_ALERT
   546  # output log_tcpdump: tcpdump.log
-----------------------------------------------------------------------------------------------------------
tail -n +524  /etc/snort/snort.conf | head -n 6                   
#   nested_ip inner, \
#   whitelist $WHITE_LIST_PATH/white_list.rules, \
#   blacklist $BLACK_LIST_PATH/black_list.rules

###################################################
----------------------------------------------------------------------------------------------------------
# Step #6: Configure output plugins
the book way.
i prefere :
└─# head -529 /etc/snort/snort.conf|tail -5                             
#   whitelist $WHITE_LIST_PATH/white_list.rules, \
#   blacklist $BLACK_LIST_PATH/black_list.rules

###################################################
# Step #6: Configure output plugins
===========================================================================================================
#NOTE we should use [ -b a ] with nl 
nl doesn't count black line while head and tails does so we should use nl -b a to count all lines.

