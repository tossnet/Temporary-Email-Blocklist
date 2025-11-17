**Temporary Email Blocklist**

A small utility designed to detect **temporary / disposable email addresse** during user registration.
This repository provides a class and a list of known disposable email providers.

**✨ Features**

Detects whether an email belongs to a disposable email service

Easy to integrate into any signup or authentication flow

Contains an extensible and maintainable domain list

**📦 Example Usage**
```csharp
$checker = new DisposableEmailChecker();

if ($checker->isDisposable($email)) {
    echo "Email rejected (temporary/disposable).";
}
```
or
```csharp
public bool IsDisposableEmail(string email)
{
    if (string.IsNullOrWhiteSpace(email)) return false;

    var parts = email.Split('@');
    if (parts.Length != 2) return false;

    var domain = parts[1];
    return DisposableEmailDomainsConfiguration.DisposableDomains.Contains(domain);
}
```

**🤝 Contributing**

Feel free to open issues or submit pull requests to add new disposable email domains or improve the detection logic.

**📜 License**

This project is licensed under the MIT License.
