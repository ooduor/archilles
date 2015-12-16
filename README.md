archilles
=========

Some quick commands I don't want to google in future coz they certainly make me look bad.

# Shuts down after 2 hours.
sudo sleep 7200s; sudo pm-suspend

# The very capable ViewSonic
* xrandr --output VGA1 --size 1600x1200
* xrandr --newmode "1600x1200_60.00"  161.00  1600 1712 1880 2160  1200 1203 1207 1245 -hsync +vsync
* xrandr --addmode VGA1 1600x1200_60.00
* xrandr --output VGA1 --mode 1600x1200_60.00

# Export only new/modified files on svn not yet checkedin
svn status | grep '^[ADMR]' | cut -b 8- | xargs -I '{}' cp --parents {} /temporary/destination/dir

# Generate db schema diagrams etc PMA is knackered on Archey
schemaspy -t mysql -db `db_name` -u root -p `password` -o `output_folder` -host localhost -dp /home/anthony/Downloads/DbToEr/mysql-connector-java-3.1.13-bin.jar


# regular use of this command to remove unneeded or unwanted packages
pacman -Rns $(pacman -Qqtd)

# control brightness of screen esp using secondary monitor
redshift -l -1.300593:36.774244 -t 6500:6500 -b 0.5

# Some need to have commands


   pacgraph  
   pacgraph --console  
   ps -ao comm,size,rss,vsize  

# Dump base64 in a string to be copy-pasted

   cat here.svg | base64 -w 0
   
# Find the top 5 mem hoggers
   $ ps -eo pmem,pcpu,vsize,pid,cmd | sort -k 1 -nr | head -5

#Just cool
tree --noreport -fp

# Create a bootable disk
sudo dd if=/home/anthony/Downloads/ubuntu-14.10-desktop-i386.iso of=/dev/sdc

# Mounting remote dir locally without key login
sshfs debian@192.168.7.2:/opt/secureapp secureapp -o PubkeyAuthentication=no

### Mounting erros esp dealing with encrypted usb drive [1]
dmsetup remove /dev/mapper/luks-77ddcd10-fd0a-4aaf-b29b-3c716522a9cf

### Stripping GPS data from photos
pacman -S perl-image-exiftool
Go to dir with the said images:
exiftool -all= -tagsfromfile @ -gps:all *.jpg

[1] http://ubuntuforums.org/showthread.php?t=1586318  
