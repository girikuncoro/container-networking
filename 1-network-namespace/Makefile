all: setup test teardown

setup:
	rm -rf setup.complete
	vagrant ssh 1-network-namespace -c 'cd /vagrant ; ./setup.sh > setup.log ; touch setup.complete' &
	until [ -f setup.complete ]; do sleep 1; done

test:
	vagrant ssh 1-network-namespace -c 'cd /vagrant ; ./test.sh'

teardown:
	rm -rf teardown.complete
	-vagrant ssh 1-network-namespace -c 'cd /vagrant ; ./teardown.sh > teardown.log ; touch teardown.complete' &
	until [ -f teardown.complete ]; do sleep 1; done

clean:
	rm -rf *.log *.complete

ssh:
	vagrant ssh 1-network-namespace
