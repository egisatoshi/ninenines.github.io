PROJECT = ninenines

DEPS = cowboy ranch bullet sheriff erlydtl yamerl
dep_cowboy = pkg://cowboy master
dep_ranch = pkg://ranch master
dep_bullet = pkg://bullet master
dep_sheriff = pkg://sheriff master
dep_erlydtl = https://github.com/evanmiller/erlydtl.git 4d0dc8fb
dep_yamerl = https://github.com/yakaz/yamerl 261da0ee

.PHONY: build clean-build run

build: clean-build deps/erlang.mk all
	@erl -pa ebin deps/*/ebin -noshell -eval 'ninenines:build(), init:stop().'

clean-build:
	@rm -rf ../index.html ../articles/ ../docs/ ../feeds/ ../support/ \
		../talks/index.html ../training/

deps/erlang.mk:
	git clone https://github.com/extend/erlang.mk deps/erlang.mk

run:
	@erl -pa ebin deps/*/ebin -noshell -eval 'ninenines:run().'

include erlang.mk
