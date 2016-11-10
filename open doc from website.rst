How to open a doc or pdf document from Odoo website?
--------------------------------------------------------------------------------------------



1) Install module Document Management System (document).

2) Create directory (knowledge menu unit) or use existing one. Attach to this category required file (button "Attachments" above the form)

3) Since it was downloaded, it would generate an url. To access it: mouse right click on downloaded file - save url

4) Add the url to the website. Pressing it will download the file (publically available).

    Note : Above Functionlity Work on odoo 8.

    Document Management System module Remove in odoo 9 community and enterprice so this all file store in ir.attachment model.

	文档管理系统在 Odoo 9 已被移除(社区版与公司版),故所有的文件均保存于  ir.attachment model 中.

So. Programatically, it is pretty much the same. The module 'document' allows to attach files to any object, including product.product (or product.template). So you have to find it(通过编程,用以下步骤实现):

attachment_ids = self.env['ir.attachment'].search([('res_model','=','product.product'),('res_id','=',product.id)]).

Where product.id - is id of needed product. E.g. you can store attachment_ids in product.product class as one2many field. After that you can get an url of any attachment. For example, for binary files:

for attach in attachment_ids: url = 'https://yourcompany.com'+'/web/binary/saveas?model=ir.attachment&field=datas&filename_field=name&id='+str(attach.id)

This url may be easily added to the website product site, using foreach in product.attachment_ids

from  http://stackoverflow.com/questions/34217000/how-to-open-a-doc-or-pdf-document-from-odoo-website

