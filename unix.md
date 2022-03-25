## find files with space and delete

  	find . -type f -name '.DS_Store' -delete

## ps -ax

	PROCESS STATE CODES
       	Here are the different values that the s, stat and state output specifiers (header "STAT" or "S") will display to describe the state of a process.
       		D    Uninterruptible sleep (usually IO)
       		R    Running or runnable (on run queue)
       		S    Interruptible sleep (waiting for an event to complete)
       		T    Stopped, either by a job control signal or because it is being traced.
       		W    paging (not valid since the 2.6.xx kernel)
       		X    dead (should never be seen)
       		Z    Defunct ("zombie") process, terminated but not reaped by its parent.

       	For BSD formats and when the stat keyword is used, additional characters may be displayed:
       		<    high-priority (not nice to other users)
       		N    low-priority (nice to other users)
       		L    has pages locked into memory (for real-time and custom IO)
       		s    is a session leader
       		l    is multi-threaded (using CLONE_THREAD, like NPTL pthreads do)
       		+    is in the foreground process group

## add numbers together

	|awk '{total = total + $1}END{print total}

## list packages

	apt list --installed

## touch all files

	find . -exec touch {} \;

## VI

	x   - delete current character
	dw  - delete current word
	dd  - delete current line
	5dd - delete five lines

	d$  - delete to end of line
	d0  - delete to beginning of line

	:1,.d
	delete to beginning of file

	:.,$d
	delete to end of file

## create 10G file

	dd if=/dev/zero of=1g.bin bs=10G count=9

## find dir

	find . -mindepth 1 -maxdepth 1 -type d

## create 100 random file

	for n in {1..1000}; do
    		dd if=/dev/urandom of=file$( printf %03d "$n" ).bin bs=1 count=$(( RANDOM + 1024 ))
	done


## find and remove files older then 5 days

	find /path/to/files* -mtime +5 -exec rm {} \;
	find /var/log/test -ctime +14 -type d -print | xargs /bin/rm -f

## find largest file

	find -type d -exec du -Sh {} +

## create a 2GB large file

	dd if=/dev/urandom of=1GB.bin bs=64M count=32 iflag=fullblock

## chown file from one user to another

	chown --from=95075 unixid * -R

