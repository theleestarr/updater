#!/bin/bash

clear
echo ' '
echo ' '
echo ' '
echo ' '
echo ' '
echo ' '
echo ' '
cat << EOF
:::    ::: :::::::::  :::::::::      ::: ::::::::::: :::::::::: :::::::::
:+:    :+: :+:    :+: :+:    :+:   :+: :+:   :+:     :+:        :+:    :+:
+:+    +:+ +:+    +:+ +:+    +:+  +:+   +:+  +:+     +:+        +:+    +:+
+#+    +:+ +#++:++#+  +#+    +:+ +#++:++#++: +#+     +#++:++#   +#++:++#:
+#+    +#+ +#+        +#+    +#+ +#+     +#+ +#+     +#+        +#+    +#+
#+#    #+# #+#        #+#    #+# #+#     #+# #+#     #+#        #+#    #+#
 ########  ###        #########  ###     ### ###     ########## ###    ###
EOF
echo ' '
echo ' '
echo ' '
echo "Ready, Set, GO!"
echo ' '
echo ' '
echo ' '
#UPDATE ALL THE THINGS!
#Runs update, upgrade, dist-upgrade, autremove. Outputs the process to the updater directory.
apt-get update -o Debug::pkgProblemResolver=true -o Debug::Acquire::http=true 2>&1 |  tee -a /home/starfury000/updater/log/"$(date +"%Y_%m_%d").log"&& apt-get -y upgrade -o Debug::pkgProblemResolver=true -o Debug::Acquire::http=true 2>&1 | tee -a /home/starfury000/updater/log/"$(date +"%Y_%m_%d").log"&& apt-get -y dist-upgrade -o Debug::pkgProblemResolver=true -o Debug::Acquire::http=true 2>&1 | tee -a /home/starfury000/updater/log/"$(date +"%Y_%m_%d").log"&& apt autoremove -y 2>&1 | tee -a /home/starfury000/updater/log/"$(date +"%Y_%m_%d").log"
#apt-get update -o Debug::pkgProblemResolver=true -o Debug::Acquire::http=true&& apt-get -y upgrade&& apt-get -y dist-upgrade&& apt autoremove -y | tee -a /home/starfury000/updater/log/"$(date +"%Y_%m_%d_%I_%M_%p").log"
echo ' '
echo ' '
echo "Update Complete"
