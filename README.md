<div align="center">

## Easy directory listing


</div>

### Description

This is an EASY example of listing files in a directory. I got this example from another post, but i could not get that post to work, so i modified it and made it easy to use. I'm using this in a new program i am working on.
 
### More Info
 


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Dustin R Davis](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/dustin-r-davis.md)
**Level**          |Intermediate
**User Rating**    |5.0 (20 globes from 4 users)
**Compatibility**  |Microsoft Visual C\+\+
**Category**       |[Complete Applications](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/complete-applications__3-7.md)
**World**          |[C / C\+\+](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/c-c.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/dustin-r-davis-easy-directory-listing__3-5019/archive/master.zip)

### API Declarations

```
#include <iostream.h>
#include <windows.h>
```


### Source Code

```
#include <iostream.h>
#include <windows.h>
int GetDir(char* dPath) {
	WIN32_FIND_DATA FileData;
	HANDLE hFile;
	hFile = FindFirstFile(dPath,&FileData);
	if ( INVALID_HANDLE_VALUE == hFile ) {
		cout << "No files" << endl;
		return false;
	}
	for ( ;; )	{
		cout << FileData.cFileName << endl;
    if ( 0 == FindNextFile(hFile, &FileData ) )
			break;
  	}
	return true;
}
int main() {
	GetDir("c:\\*.txt");
	return true;
}
```

