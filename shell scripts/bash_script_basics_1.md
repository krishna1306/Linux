### For Loop

```bash
for mission in <list-of-missions>
do
	create-and-launch-rocket $mission
done
```

`<list-of-missions>` can be a simple list separated by spaces

```bash
for mission in lunar-mission mars-mission jupiter-mission
do
	create-and-launch-rocket $mission
done
```

#### Get the list from a file that has the list (one item per line)

```bash
for mission in `cat mission-names.txt`
do
	create-and-launch-rocket $mission
done
```

#### For loop with a specified integer limit

```bash
for mission in {0..100}
do
	create-and-launch-rocket mission-$mission
done

for mission in `seq 1 100`
do
	create-and-launch-rocket mission-$mission
done
```

Or, can also be done in a traditional `C` like way

```bash
for (( mission = 0 ; mission <= 100 ; mission++ ))
do
	create-and-launch-rocket mission-$mission
done
```

#### Real Life Examples

```bash
for file in $(ls)
do
	echo Line count of $file is $(cat $file | wc -l)
done

for package in $(cat packages.list)
do
	sudo apt-get -y install $package
done

for server in $(cat servers.list)
do
	ssh $server "uptime"
done
```

---

#### Kode Kloud Exercise - Good one

```bash
for file in $(ls /home/bob/images)
do
        echo $file
        if [[ $file = *.jpeg  ]]
        then
                new_name=$(echo $file | sed 's/jpeg/jpg/g')
                mv images/$file images/$new_name
        fi
done
```

### While Loop

```bash
while [ $rocket_status = "launching" ]
do
	sleep 2
	rocket_status=rocket_status $mission_name
done
```

### Case Statements

```bash
case $choice in
	1) shutdown now
		 ;;
	2) shutdown -r now
  	 ;;
	3) break
		 ;;
	*) continue 
		 ;;
esac
```

