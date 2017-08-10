pdftk use
============

#. 导出和更新pdf的bookmark
   pdftk 01.pdf dump_data output doc_data.txt
   pdftk 01.pdf update_info doc_data.txt output 02.pdf
