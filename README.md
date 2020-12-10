## Mature vs cutting edge:

A key factor to consider when picking any technology is maturity. Bellow table shows a comparison of the initial release dates and current version number

|   |  Initial release |Current version   |
|---|---|---|
|Terraform   | 2014  |  v0.14.0 |
|Terragrunt   | 2014  | v0.26.7  |
| Terraspace  | 2016  | v0.5.8  |

Initial release
Current version
Terraform
2014
v0.14.0
Terragrunt
2014
v0.26.7
Terraspace
2016
v0.5.8

this is not an apples-to-apples comparison, since different tools have different versioning schemes. Terraspace is , the youngest IAC tool in this comparison. This is Terraspace’s biggest weakness. the price you pay for using this new, cutting-edge tool is that it is not as mature as some of the other IAC options.

Large community vs small community:
Whenever you pick a technology, you are also picking a community. In many cases, the ecosystem around the project can have a bigger impact on your experience than the inherent quality of the technology itself. The community determines how many people contribute to the project, how many plugins, integrations, and extensions are available, how easy it is to find help online (e.g. blog posts, questions on StackOver‐ flow)



Contributers
stars
StackOverflow
Terraform
1528
24.7k
6927
Terragrunt
138
4.5k
84
Terraspace
?
82
0
Obviously, this is not a perfect apples-to-apples comparison.




Let's deep-dive more:
Terraspace has a better structure. Without any pain, Terraspace build this beautiful structure for you and the awesome thing about terraspace is how it handles layering.
You can read about layring in this blog.


Another cool thing about terraspace is .terraspace-cache. Terraspace works by building files in the app and config/terraform folders to a .terraspace-cache folder. Then it merely calls out to terraform within that folder.
In fact, you can use Terraspace to build the files first, cd into the .terraspace-cache folder, and run Terraform directly. Example:
# terraspace build demo
# cd .terraspace-cache/us-west-2/dev/stacks/demo
# terraform init
# terraform apply
 
Once you’re in the .terraspace-cache folder, it’s regular terraform at that point.
Terraspace automates it with:
# terraspace up demo

Let’s see what is inside .terraspace-cache. As you can see terraspace automatically puts the config file into .terraspace-cache . it substitutes your variable with a proper value so it helps you to debug your code better.



Installation:
First we should install ruby.
insrall ruby

#sudo apt-get install -y libreadline-dev zlib1g-dev
#apt-get install -y libssl-dev
#apt-get install build-essential
#git clone https://github.com/rbenv/rbenv.git ~/.rbenv
#echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.bashrc
#echo 'eval "$(rbenv init -)"' >> ~/.bashrc
#exec $SHELL
#git clone https://github.com/rbenv/ruby-build.git "$(rbenv root)"/plugins/ruby-build
#rbenv install 2.7.1

It takes some time to complete the installation. You can see the process like bellow.
cd /tmp
tail -f ruby-build.20201207235452.3413.log



rbenv install 2.7.1
rbenv global 2.7.1


ruby -v


Then we should install Terraspace.
Install Terraspace


As you can see Terraspace needs Terraform so we should install it.

#sudo apt-get install wget unzip -y

#sudo wget https://releases.hashicorp.com/terraform/0.12.18/terraform_0.12.18_linux_amd64.zip

#sudo unzip terraform_0.12.18_linux_amd64.zip
#sudo mv terraform /usr/local/bin/

#terraform -v
Terraform v0.12.28






Conclusion:
 Although Terragrunt has a better community and we can find more examples on Github but Terraspace has a better structure. We can start with Terraspace and if we have trouble because of a lack of examples or documents we can switch to Terragrunt very fast.







