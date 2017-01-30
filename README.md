# coursebuilder-register-handler-unicode
To allow unicode characters to be displayed as they should when parsed by the registration handler

Line #1193 in this code has a change to the original

Original:
name, transforms.dumps(self.request.POST.items()), self,

Change:
name, transforms.dumps(self.request.POST.items()).decode('unicode_escape'), self,

The decode method with the parameter of 'unicode_escape' was added to POST items that are received from the registration form.
This is to allow unicode characters to be displayed as is in the additional_fields field for the Student datastore.
The comment at Line #1190 explains this.

Please note that if you do not use the additional_fields in the Student datastore, then this will not affect you.
