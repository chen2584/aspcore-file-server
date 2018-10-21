# aspcore-file-server

หากมีืชื่อโฟวเดอร์เหมือนกัน จะยึด middleware ที่ทำงานก่อนเป็นหลัก เช่น MyFile ใน root folder และ MyFile ในโฟวเดอร์ wwwroot หากยึดตามโค้ดข้างล่าง ASP.NET Core จะอ่านไฟล์ในโฟวเดอร์ wwwroot

```
app.UseStaticFiles();
app.UseFileServer(new FileServerOptions
{
    FileProvider = new PhysicalFileProvider(Path.Combine(env.ContentRootPath, "MyFile")),
    RequestPath = "/MyFile",
    //EnableDirectoryBrowsing = true
});
```