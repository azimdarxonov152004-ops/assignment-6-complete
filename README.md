#include <linux/module.h>
#include <linux/kernel.h>
#include <linux/init.h>

MODULE_LICENSE("GPL");
MODULE_AUTHOR("Azim Darxonov");
MODULE_DESCRIPTION("Simple hello kernel module for Coursera Assignment 6");

static int __init hello_init(void) {
    printk(KERN_INFO "Hello from Coursera Embedded Linux Course!\n");
    return 0;
}

static void __exit hello_exit(void) {
    printk(KERN_INFO "Goodbye from Coursera course!\n");
}

module_init(hello_init);
module_exit(hello_exit);
obj-m += hello.o

all:
	make -C /lib/modules/$(shell uname -r)/build M=$(PWD) modules

clean:
	make -C /lib/modules/$(shell uname -r)/build M=$(PWD) clean
  git init
git add .
git commit -m "Assignment 6 complete – simple kernel module"
git branch -M main
git remote add origin https://github.com/SIZNING_USERNAME/SIZNING_REPO_NOMI.git
git push -u origin main

# Keyin tag qo‘shing
git tag assignment-6-complete
git push origin assignment-6-complete
  
