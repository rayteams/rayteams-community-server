# rcs.process

## Introduction

Process/Software를 관리해주는 Module

## Process

### Monitoring

**Description**

특정 ProcessName을 모니터링한다.

* Method Name : ```rcs.process.monitoring```
* Response Name 
  * ```rcs.process.monitoring.[REPLYTO].notrunning```
  * ```rcs.process.monitoring.[REPLYTO].result```


**RestAPI**

```
// Bacic usage
{
	"command" : "rcs.process.monitoring",
	"data" : {
		"processName" : "Notepad.exe"
	}
}
```

**Features**

* Module config에서 Process scan의 Interval을 설정할 수 있다.(Default : 5초)


### Run

**Description**

특정 Software를 실행시킨다.

* Method Name : ```rcs.process.run```
* Response Name 
  * ```rcs.process.run.[REPLYTO].success```
  * ```rcs.process.run.[REPLYTO].exit```
  * ```rcs.process.run.[REPLYTO].error```

**RestAPI**

```
// Bacic usage
{
	"command" : "rcs.process.run",
	"data" : {
		"exePath" : "C:\\Ray\\RAYTeams\\RAYTeams.exe"
	}
}
// With parameters
{
	"command" : "rcs.process.run",
	"data" : {
		"exePath" : "C:\\Ray\\RAYTeams\\RAYTeams.exe",
		"exeOption" : [
			"-d", "dValue", "-c", "cValue"
		]
	}
}
// Receive output message
{
	"command" : "rcs.process.run",
	"data" : {
		"exePath" : "C:\\Ray\\RAYTeams\\RAYTeams.exe",
		"exeOption" : [
			"-d", "dValue", "-c", "cValue"
		],
		"output" : true
	}
}
```

**Features**

* ```exePath``` 의 값만 넣어주면 된다.
* 실행은 RCS의 실행 권한과 동일한 실행 권한으로 실행된다.


### KillProcessByName

**Description**

ProcessName으로 해당 Process를 종료시킨다.

* Method Name : ```rcs.process.killbyname```
* Response Name 
  * ```rcs.process.killbyname.[REPLYTO].success```

**RestAPI**

```
// Bacic usage
{
	"command" : "rcs.process.killbyname",
	"data" : {
		"processName" : "Notepad.exe"
	}
}
```

**Features**

* 

### Kill

**Description**

특정 Process ID를 종료시킨다.

* Method Name : ```rcs.process.kill```
* Response Name 
  * ```rcs.process.kill.[REPLYTO].success```

**RestAPI**

```
// Bacic usage
{
	"command" : "rcs.process.kill",
	"data" : {
		"pid" : 1234
	}
}
```

**Features**

* 