<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Cloud Security with AWS IAM

**Author:** Ajibola Ogunbanwo
**Email:** ajibolaimpo@gmail.com

---

![Image](http://learn.nextwork.org/affectionate_brown_timid_maracuja/uploads/aws-security-iam_1c864649)

---

## Introducing Today's Project!

### Project overview

In this project, I will demonstrate how to use Identity Access and Management using AWS. I'm doing this project to learn how to use IAM on AWS and to build my technical skills for the future.

### Tools and concepts

Services I used were EC2, User Groups, Users and IAM JSON Policy. Key concepts I learnt include how to assign users to IAM groups, how to create an IAM user, How to set up IAM policies, and how to test is that policy is working. 

### Project reflection

This project took me approximately. 2 hours. The most challenging part was creating the IAM Policy. It was most rewarding to finally finish this and get a little more used to the AWS console.

---

## Tags

### What I did in this step

In this step, I will launch a EC2 instance because I want to increase my computing power to match the increased traffic that my site will get.


### Understanding tags

Tags are used to name your instances and be able to search for them when needed. This is important in a large scale company.

### My tag configuration

The tag I’ve used on my EC2 instances is called Env. The value I’ve assigned for my instances are development and production. 

![Image](http://learn.nextwork.org/affectionate_brown_timid_maracuja/uploads/aws-security-iam_2e0e5a5d)

---

## IAM Policies

### What I did in this step

In this step, I will create a AWS IAM policy because I want to give new interns access to the development but not production.

### Understanding IAM policies

IAM Policies are rules for who can do what your AWS resources. It sets permissions and gives certain people access to certain things.

### The policy I set up

For this project, I’ve set up a policy using JSON.

### Policy effect

I’ve created a policy that allows for anyone to use or modify ec2 resources that are under the Env with the development tag.

### Understanding Effect, Action, and Resource

The Effect, Action, and Resource attributes of a JSON policy means 3 different things. Effect is either deny or allow and deny has the priority over allow. Action defines what actions the effect is allowing or denying. The resource defines which resources the policy applies to.

---

## My JSON Policy

![Image](http://learn.nextwork.org/affectionate_brown_timid_maracuja/uploads/aws-security-iam_1c864649)

---

## Account Alias

### What I did in this step

In this step, I will create an Account Alias because this way I can simplify user login.

### Understanding account aliases

An account alias is a name that you can have to help login instead of a long AWS account username.

### Setting up my account alias

Creating an account alias took me 2 min. Now, my new AWS console sign-in URL is https://nextwork-alias-ajibolaogunbanwo.signin.aws.amazon.com/console

![Image](http://learn.nextwork.org/affectionate_brown_timid_maracuja/uploads/aws-security-iam_0eb4439b)

---

## IAM Users and User Groups

### What I did in this step

In this step, I will create a dedicated IAM group for Interns because they should not have the same permissions and everyone else. I will also set up an IAM user for this new intern as well.

### Understanding user groups

IAM user groups are group where you can assign the polices we set before. We can simply just add users into this group now instead of making the policy new for every user.

### Attaching policies to user groups

I attached the policy I created to this user group, which means this group now has to adhere to the policy I've set.

### Understanding IAM users

IAM users are users that need to be assigned to a certain group with their own set policies. 

---

## Logging in as an IAM User

### Sharing sign-in details

The first way is you can give them their console sign-in URL, or you can email them sign in instructions.

### Observations from the IAM user dashboard

Once I logged in as my IAM user, I noticed I cannot do much as a lot of things already had access denied This was because of the IAM policy we set earlier.

![Image](http://learn.nextwork.org/affectionate_brown_timid_maracuja/uploads/aws-security-iam_6f2ab446)

---

## Testing IAM Policies

### What I did in this step

In this step, I will test the intern's IAM user because we want to make sure they have the correct access to only the devlopement and not the production.

### Testing policy actions

I tested my JSON IAM policy by going into my IAM user and logging in. I tried to stop my production EC2 instance and it did not work.This is due to my IAM policy.

### Stopping the production instance

When I tried to stop the production instance I was met with a huge red error message. This was because the policy we set before does not give us access to do this.

![Image](http://learn.nextwork.org/affectionate_brown_timid_maracuja/uploads/aws-security-iam_0e7a9d6a)

### Stopping the development instance

Next, when I tried to stop the development instance it was successful. This was because my JSON IAM Policy allows for this to happen.

![Image](http://learn.nextwork.org/affectionate_brown_timid_maracuja/uploads/aws-security-iam_1811801c)

---

## IAM Policy Simulator

To extend my project, I'm going to use a IAM tool called the Policy Simulator to check my policies. I'm doing this because I do not want to affect my actual AWS resources just to check if my policy works. 

### Understanding the IAM Policy Simulator

The IAM Policy Simulator is used to check what your user can do and if your policy is in place. It's useful for checking if your JSON IAM policy is actually working without interupting anything else.

### How I used the simulator

I set up a simulation for EC2 and the action was deletetags and stopintances. The results were both were denied. I had to adjust stopinstances to include the development part becasue interns can actually be able to do that.

![Image](http://learn.nextwork.org/affectionate_brown_timid_maracuja/uploads/aws-security-iam_069d8a621)

---

---
