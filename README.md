# Joomla!LABS Update Servers

This repository contains the XML manifest files for the Joomla! update server system, providing automatic update notifications for Joomla!LABS extensions.

## 📋 Overview

Joomla! uses an update server system to notify users when new versions of extensions are available. Each XML file in this repository defines the available versions, download locations, compatibility requirements, and security checksums for a specific extension.

## 🔧 How It Works

When a Joomla!LABS extension is installed, it registers the update server URL pointing to the corresponding XML file in this repository. Joomla periodically checks these XML files to:

1. **Detect new versions** - Compare installed version with available releases
2. **Verify compatibility** - Check Joomla and PHP version requirements
3. **Validate security** - Verify SHA256/SHA384/SHA512 checksums
4. **Provide updates** - Offer one-click installation of new versions

## 📁 XML Structure

Each update server XML file follows the Joomla! update manifest format:

```xml
<updates>
    <update>
        <name>Extension Name</name>
        <version>x.x.x</version>
        <targetplatform name="joomla" version="[456]\.[0-9]+" />
        <php_minimum>8.1</php_minimum>
        <downloads>
            <downloadurl type="full" format="zip">...</downloadurl>
        </downloads>
        <sha256>...</sha256>
        <sha384>...</sha384>
        <sha512>...</sha512>
    </update>
</updates>
```

### Key Elements

- **`<targetplatform>`**: Regex pattern defining compatible Joomla versions
- **`<php_minimum>`**: Minimum required PHP version
- **`<sha256/384/512>`**: Security checksums for package verification
- **`<section>`**: Update category (STS = Security/Stable)

## 🚀 Usage

### For Extension Developers

To use these update servers in your Joomla!LABS extension, add the server URL to your extension's manifest XML:

```xml
<updateservers>
    <server type="extension" priority="1" name="Extension Name">
        https://raw.githubusercontent.com/JoomlaLABS/updateservers/main/mod_example.xml
    </server>
</updateservers>
```

### For End Users

Updates are handled automatically by Joomla!:
1. Navigate to **System → Update → Extensions**
2. Click "Find Updates" to check for new versions
3. Install available updates with one click

## 🔒 Security

All release packages include SHA256, SHA384, and SHA512 checksums for integrity verification. Joomla automatically validates these hashes before installing updates.

## 📚 Documentation

- [Joomla! Deployment Documentation](https://docs.joomla.org/Deploying_an_Update_Server)
- [Managing Component Updates](https://docs.joomla.org/J4.x:Managing_Component_Updates)
- [Update Server Specification](https://docs.joomla.org/Specification_of_the_update_server_XML_file)

## 🤝 Contributing

We welcome contributions! Here's how you can help:

### 🔄 How to Contribute

1. **🍴 Fork** the repository
2. **🌿 Create** a feature branch (`git checkout -b feature/amazing-feature`)
3. **✨ Make** your changes following our coding standards
4. **🧪 Add** tests if applicable
5. **💾 Commit** your changes (`git commit -m 'Add some amazing feature'`)
6. **🚀 Push** to the branch (`git push origin feature/amazing-feature`)
7. **📮 Submit** a pull request

### 📋 Guidelines

- Follow PSR-12 coding standards for PHP code
- Write clear, concise commit messages
- Test your changes thoroughly before submitting
- Update documentation as needed
- Ensure your code is well-documented with inline comments
- Maintain security best practices

## 📄 License

This project is licensed under the **GNU General Public License v2.0** - see the [LICENSE](LICENSE) file for details.

```
GNU GENERAL PUBLIC LICENSE
Version 2, June 1991

Copyright (C) 2023-2025 Joomla!LABS

This program is free software; you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation; either version 2 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the
GNU General Public License for more details.
```

All update manifests are provided under the same license as their corresponding extensions.

## 👥 Project Information

### 🏢 Project Owner

**Joomla!LABS** - [https://joomlalabs.com](https://joomlalabs.com)

[![Email](https://img.shields.io/badge/Email-info%40joomlalabs.com-red?style=for-the-badge&logo=gmail&logoColor=white)](mailto:info@joomlalabs.com)

*Joomla!LABS is the company that owns and maintains this project.*

### 👨‍💻 Contributors

**Luca Racchetti** - Lead Developer

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Luca%20Racchetti-blue?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/razzo/)
[![GitHub](https://img.shields.io/badge/GitHub-Razzo1987-black?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Razzo1987)

*Full-Stack Developer passionate about creating modern, efficient web applications and tools for the Joomla! community*

## 🆘 Support

### 💬 Get Help

Need help? We're here for you!

- 🐛 **Found a bug?** [Open an issue](https://github.com/JoomlaLABS/updateservers/issues/new?labels=bug&template=bug_report.md)
- 💡 **Have a feature request?** [Open an issue](https://github.com/JoomlaLABS/updateservers/issues/new?labels=enhancement&template=feature_request.md)
- ❓ **Questions?** [Start a discussion](https://github.com/JoomlaLABS/updateservers/discussions)

## 💝 Donate

If you find this project useful, consider supporting its development:

[![Sponsor on GitHub](https://img.shields.io/badge/Sponsor-GitHub-ea4aaa?style=for-the-badge&logo=github)](https://github.com/sponsors/JoomlaLABS)
[![Buy me a beer](https://img.shields.io/badge/🍺%20Buy%20me%20a-beer-FFDD00?style=for-the-badge&labelColor=FFDD00&color=FFDD00)](https://buymeacoffee.com/razzo)
[![Donate via PayPal](https://img.shields.io/badge/Donate-PayPal-0070BA?style=for-the-badge&logo=paypal&logoColor=white)](https://www.paypal.com/donate/?hosted_button_id=4SRPUJWYMG3GL)

Your support helps maintain and improve this project!

---

**Made with ❤️ for the Joomla! Community**

**⭐ If this project helped you, please consider giving it a star! ⭐**