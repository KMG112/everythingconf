1. Explain how AWS differs from other services, such as Heroku
2. Show an example
3. Reference documentation or tutorials on AWS S3 to store file uploads

<h1>EXPLAIN!</h1>
```
<h2>Write down keys in Figaro</h2>


AWS_ACCESS_KEY_ID: NUNNAURBIZZNEZZ
AWS_SECRET_ACCESS_KEY: IAMAWESOMEYOUAREAWESOMETOOIGUESS

S3_BUCKET: fuckit



<h2>In the config/initializers folder</h2>


AWS.config(
  :region => 'us-east-1',
  :access_key_id => ENV['AWS_ACCESS_KEY_ID'],
  :secret_access_key => ENV['AWS_SECRET_ACCESS_KEY']
)


S3_BUCKET =  AWS::S3.new.buckets[ENV['S3_BUCKET']]



<h2>Pushing Objects</h2>
    obj = S3_BUCKET.objects["collage.png"] #creates object in AWS bucket

    obj.write(
      file: 'public/collage.png',
      acl: :public_read
    )#writes item to AWS bucket
 ```

<a href="https://github.com/aws/aws-sdk-ruby"> AWS_SDK docs</a>