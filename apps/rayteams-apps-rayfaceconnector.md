# rayteams-apps-rayfaceconnector

## Introduction

RAYFace Software를 연결하여 주요 정보들을 요청/가져오는 App

아래의 Function들을 이용하기 위해서는 RCS에서 제공하는 방법으로 이용할 수 있습니다.

이와 관련된 정보는 [App](./README.md) 정보를 확인하시기 바랍니다.

## Patients

### GetPatients

**Description**

환자의 정보를 가져온다.

* Method Name : ```rcs.apps.rayfaceconnector.getpatients```
* Response Name 
  * ```rcs.apps.rayfaceconnector.getpatients.[REPLYTO].success```
  * ```rcs.apps.rayfaceconnector.getpatients.[REPLYTO].fail```


**RestAPI**

```
// Bacic usage
{
	"command" : "rcs.apps.rayfaceconnector.getpatients",
	"data" : {}
}

// with Filter
{
	"command" : "rcs.apps.rayfaceconnector.getpatients",
	"data" : {
		{
			"project" : ["pid", "full_name"],
			"filter":{
				"gender":"male"
			}
		}
	}
}
```

**Features**

* filter에 정의된 key, value는 완전히 일치하는 Patient를 가져온다.


### GetPatientsByName

**Description**

환자의 정보를 이름으로 검색한 결과를 가져온다. 

* Method Name : ```rcs.apps.rayfaceconnector.getpatientsbyname```
* Response Name 
  * ```rcs.apps.rayfaceconnector.getpatientsbyname.[REPLYTO].success```
  * ```rcs.apps.rayfaceconnector.getpatientsbyname.[REPLYTO].fail```

**RestAPI**

```
// Bacic usage
{
	"command" : "rcs.apps.rayfaceconnector.getpatientsbyname",
	"data" : {
		"name" : "승"
	}
}
```

**Features**

* name의 값이 존재하는 모든 Patient를 가져온다.


### GetPatientsByGender

**Description**

지정한 성별에 해당하는 Patient를 가져온다.

* Method Name : ```rcs.apps.rayfaceconnector.getpatientsbygender```
* Response Name 
  * ```rcs.apps.rayfaceconnector.getpatientsbygender.[REPLYTO].success```
  * ```rcs.apps.rayfaceconnector.getpatientsbygender.[REPLYTO].fail```

**RestAPI**

```
// Bacic usage
{
	"command" : "rcs.apps.rayfaceconnector.getpatientsbygender",
	"data" : {
		"gender" : "male"
	}
}
```

**Features**

* gender 의 값은 ```male, female, other``` 가 존재한다.

### GetPatientsByBOD

**Description**

지정한 생년월일이 일치하는 Patent를 가져온다.

* Method Name : ```rcs.apps.rayfaceconnector.getpatientsbybod```
* Response Name 
  * ```rcs.apps.rayfaceconnector.getpatientsbybod.[REPLYTO].success```
  * ```rcs.apps.rayfaceconnector.getpatientsbybod.[REPLYTO].fail```

**RestAPI**

```
// Bacic usage
{
	"command" : "rcs.apps.rayfaceconnector.getpatientsbybod",
	"data" : {
		"bod" : "2022-11-02"
	}
}
```

**Features**

* bod(Birth-Of-Day)의 값은 YYYY-MM-DD 형식이다.


## Projects

RAYFace 의 Project/Case 정보는 매우 많은 정보를 담고 있다.

이에, 필요한 요소만 지정하여 정보를 얻을 수 있는데, 필요한 요소를 지정하지 않은 경우에는 Default Projection 이 적용된다.

**Default Prjection**

```["hd_recon","is_projected","pid","scan_data_path","scan_date","scan_time","version","reconstructed","reconstructed_smile","last_access_time"]```

### GetProjects

**Description**

RAYFace Project를 가져온다.

* Method Name : ```rcs.apps.rayfaceconnector.getprojects```
* Response Name 
  * ```rcs.apps.rayfaceconnector.getprojects.[REPLYTO].success```
  * ```rcs.apps.rayfaceconnector.getprojects.[REPLYTO].fail```

**RestAPI**

```
// Bacic usage
{
	"command" : "rcs.apps.rayfaceconnector.getprojects",
	"data" : {
		"filter" : { 
			"pid" : "PID2018-00006" 
		},
		"project" : ["scan_data_path","hd_recon"]
	}
}
```

**Features**


### GetProjectsByPID

**Description**

RAYFace Project를 가져온다.

* Method Name : ```rcs.apps.rayfaceconnector.getprojectsbypid```
* Response Name 
  * ```rcs.apps.rayfaceconnector.getprojectsbypid.[REPLYTO].success```
  * ```rcs.apps.rayfaceconnector.getprojectsbypid.[REPLYTO].fail```

**RestAPI**

```
// Bacic usage
{
	"command" : "rcs.apps.rayfaceconnector.getprojectsbypid",
	"data" : {
		"pid" : "PID2018-00006" 
	}
}
```

**Features**

