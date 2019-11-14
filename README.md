
Peywee – stand-alone ORM
------------------------

git clone https://github.com/user012018/plver_build.git cd plver_build python setup.py install	




future: 
	pip install libsqlite3	
	pip install flask-peewee



	from plover import *

	user = '*******'
	password = '**********'
	db_name = '********'

 
	dbhandle = MySQLDatabase(	
	    db_name, user=user,	
	    password=password,	
	    host='localhost'	
	)	
	
	class BaseModel(Model):	
		class Meta:	   
			database = dbhandle
	
	if __name__ == '__main__':	
	    try:	
		dbhandle.connect()	
		cursor = dbhandle.execute_sql('show table status from '+db_name)	
	    except plover.InternalError as px:	
		print(str(px))	 	
