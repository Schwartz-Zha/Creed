# Creed of Beggar Gang: A Budget-efficient Approach to Deep Learning Hardware in University Research


This project aims to provide a recommended approach for university researchers to purchase deep learning hardware in a budget efficient way. Since the authors are based in Hong Kong, all figures on money mentioned here will be in Hong Kong Dollar (HKD). Since HKD is pegged to US Dollar (USD), you can simply convert by 7.8 HKD $\approx$ 1 USD if you are more familiar with USD.

For university researchers, budget has, is and will always be an issue, especially for innovations on deep learning, including CV, NLP, ML etc. GPU computing power is critical in these areas for almost any potential innovation, and junior students also need frequent access to adequate GPUs to basically get familiar existing methods. It is recommended that a princicpal researcher should purchase different level of GPUs for different purposes, use NVIDIA Server GPU (A100, A800, A40) for cutting edge research and consumer level level GPU (RTX4090, RTX3090) for simpler tasks. 

Usually, the overall budget is limited, so it is recommended to have enough amount of cheap consumer level GPUs before moving to spend on expensive server GPU. With limited resources, "quantity is the best quality", as quoted from Joseph Stalin during WW2. 


This explains the core idea of this approach, we are not actually poor, but we want to make sure every penny plays an important role in our future breakthroughs in research. More specifically, We try to purchase a easy to use 4U rackmount GPU server with 8 GPUs with least amount of money, also meeting the usual requirements of common university hardware management such as power safety and warrenty.  


## Chassis (Rackmount or Tower)
Modern GPU consumes a lot of power to run in full speed, thus requires a strong cooling method. For safety and life span concern, water liquid is never considered here. So the whole setup is very noise, and usually has to be put inside a dedicated server room. Hence, rackmount server is more convenient, and easier to manage the cables. Also, rackmmount server will easily hold 8 GPUs with very good airway, enabling the GPUs to work better in full speed.


We found one chassis specifically designed for this purpose, with a very affordable price.

[ASUS ESC8000A-E11](https://servers.asus.com/products/Servers/GPU-Servers/ESC8000A-E11)

The corresponding Intel Xeon version is 

[ASUS ESC8000-E11](https://servers.asus.com/products/servers/gpu-servers/ESC8000-E11)

Another good thing about this type of chassis is, they support up to 8 x 3.5'' drive drives, providing sufficient storage space for common deep learning tasks. 

You can also check on another major manufacturor in server domain, supermicro. And they have 

[A+ Server 4124GS-TNR](https://www.supermicro.com/en/Aplus/system/4U/4124/AS-4124GS-TNR.cfm)

Supermicro actually takes a stronger position in the whole market share of servers. So they only offer a complete system, meaning you have to buy everything including CPU, GPU, memory... all from a certified supermicro dealer. But this chassis does support up to 24 x 2.5'' hard drives, making it capable of hosting more starage than a normal dedicated storage server. But you might need to pay a higher overall price since your choice is limited to a complete system.

## Power Supply
All chassis mentioned here support 2+2 redundant power supply, and we recommend 2200W power unit to feed 8GPU, 2CPU and the onboard cooling fans. The price of power supply units are usually very low, compared to other parts in this machine, so you do not need to pay too much attention. Just make sure it provides enough output power or your machine will randomly shutdown itself.

## CPU (Intel Xeon or AMD EPYC)
Specific comparisons have to be made between specific models, here we only give some general experience. 

Server market has always been dominated by Intel ever since the formation of this market. AMD has never been an important player on the server market before the introduction of ZEN microarchitecture, thanks to Jim Keller, who is like your go-to guy whenever your chips are not popular on market. Zen 1 is also EPYC 1st gen, which does have a few technical problems, very understandable from an engineering perspective. Then it comes to ZEN 2, and EPYC 2nd gen, which really makes AMD stand firmly in this market. People had never seen a server CPU that has 64C128T before (the best was 28C56T of Intel Xeon), and Oracle was claiming that they were gonna charge twice the price for a single machine but with a 64C CPU. So you get the idea, EPYC 2nd was a huge leap, builing the technical advantage of EPYC over Xeon ever since. 

However, Intel Xeon CPU still have one important feature that has not yet been provided EPYC. Xeon CPUs could be inter-connected by dozens. This is an important feature when building a CPU cluster. But for us, who mainly relies on GPU to work, this is unimportant. We usually only need 2CPU to support 8GPU. (1CPU is also possible). 

Another feature that makes me prefer EPYC over Xeon is that, AMD has never designed any on-board auxialiary chip, while Intel often splits some onboard communication tasks from the CPU to a small chip embedded onboard. This actually slows down the communication, and such communication happens a lot in deep learning training cycles.  

Every generation of EPYC provides 5 types of CPU, and they are simply

| 16C32T | 24C48T | 32C64T | 48C96T | 64C128T |
|--------|--------|--------|--------|---------|

A very clean and neat line of products. For 8GPUs, 2 x 16C32T is good enough for normal images tasks. But reinforcement learning algorithms may requrie a lot more core number because it needs much more threads to train. 

Also, if your budget is limited, we recommend you go with EPYC 2nd gen, which is already good enough. You will not get a significant performance boost by spending a lot more on EPYC 3rd, 4th and 5th gen. 

## Memory
Server memories are generally very cheap, get something with "ECC" and "RDIMM" will be good. We use 8 x

[Samsung 32GB ECC DIMM Server RAM](https://semiconductor.samsung.com/dram/module/rdimm/m393a4k40db3-cwe/)

## Hard Drive
Definitely need some SSD to speed things up. Since such machines are usually on 24x7, you are recommended not to save on the SSD where your operating system resides on. If that SSD breaks, you are in high-risk of losing all data on that disk and all other disks. So, we prefer "datacenter" level SSD, and one good product is 

[Sumsang pm9a3 Datacenter SSD](https://semiconductor.samsung.com/ssd/datacenter-ssd/pm9a3/)

For other storage requriements on datasets, model checkpoints, feel free to select anything on SSD or HDD, they usually will not be the bottleneck.


## GPU
To put 8 GPUs into this system, every GPU has to be 2-slot width. All sever GPUs are 2-slot width, and consumer level GPUs must be blower-type (sometimes they can be hard to found). Since this is a budget limited build, we place 8 x

[Gigabyte Blower RTX 3090](https://www.tomshardware.com/news/gigabyte-geforce-rtx-3090-blower-gpu)

Giagabyte withdraws this product from their official website, due to pressure from NVIDIA. NVIDIA sets restriction that all of their consumer level GPUs should be dedicated for gaming, not for production usage. (university research is not considered production and thus exempted). And in fact, no gamer will buy a blower 3090 because it is too noisy. So, yeah, such approach to save some money may not work in the future, and you have to buy severl level GPUs from NVIDIA. 

## Overall cost 
As of May 2023, the overall price for a build like this is 126000 HKD ( $\approx$ 16000 USD). 

## Communication annd Discussion
If you have a better plan, or any concerns/comments/discussions you would like to make, you are free to contact me by [email](mailto:jiajun.zha@connect.ust.hk), but we prefer that you could open an issue on this project. We believe in the value of open discussion.