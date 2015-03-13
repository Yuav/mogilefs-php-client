**UPDATE**:

I have taken this client a step further, and created a MogileFS PHP Model library which abstracts the file stored in MogileFS:

https://github.com/Yuav/MogileFS-PHP-Model

Hopefully you'll find it useful :)


---


I am struggling with a high latency network, and in many cases the tracker simply doesn't respond in time, and the client throws a fatal error. So I did some modifications on the client from http://osterman.com/wordpress/2007/06/30/robust-php-mogilefs-client

Changelog:
  * added getFile function
  * added FILE\_INFO capable function (Thanks Jan Kantert)
  * setFile now tries upload 3 times before failing - example; tracker dies during upload
  * setResource with key == null now close file handle before throwing exception
  * added pathcount and noverify options to getPaths (copied from perl client 1.08)
  * unknown key, and empty file now produce a warning, and not fatal error in doRequest

My plan was to make it slightly more tolerant for errors from tracker.

You can download it here: <a href='https://mogilefs-php-client.googlecode.com/files/mogilefs.class.31.07.2011.php.txt'>MogileFS PHP Client</a>