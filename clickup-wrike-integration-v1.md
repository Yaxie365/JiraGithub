# ClickUp Wrike integration

Connecting ClickUp with Wrike keeps task data aligned between teams that plan and track work in different tools. Getint synchronizes tasks, statuses, comments, and attachments between both platforms automatically, removing manual updates and duplicate entries.

This guide walks you through the setup step by step and lists the restrictions that apply to this integration.

## Requirements to Build Your Integration

* **Deployment Options**: Getint provides two ways to host your integration: a managed [SaaS platform](https://app.live.getint.io/) or a self-hosted On-premise version. More information about Getint On-premise [here](https://docs.getint.io/getting-started-with-the-platform/deployment-options/on-premise-deployment).
* **Authentication**: ClickUp requires a personal API token and Wrike requires a Permanent Access Token. You can find the steps to generate both tokens here: [Connection Guide](https://docs.getint.io/guides/quickstart/connection#clickup).
* **Service Accounts**: Because the integration attributes comments to the user who created the connection, we recommend using dedicated Service Accounts in both tools to keep a clear distinction between automated updates and individual user activity.

## Setting Up Your ClickUp Wrike Integration

### 1. Access the Getint App

* Log in at [app.live.getint.io](http://app.live.getint.io/). If you do not have an account, click **Sign up** to create one.

<figure><img src="https://4106311246-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MR6Z9V8zLATPQPOGSDf%2Fuploads%2FTjpUT3cfnYSIc8hpVaHO%2FApp.getint.io%20account%20creation.png?alt=media&amp;token=9c3c9724-99f4-4b41-b17a-faf3a9f125e0" alt=""><figcaption></figcaption></figure>

* Enter your details, select the apps you want to connect, and click **Create new workspace**.

<figure><img src="https://4106311246-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MR6Z9V8zLATPQPOGSDf%2Fuploads%2FCKZpPDxbiykHAeNaIP7K%2FCreate%20a%20new%20workspace.png?alt=media&amp;token=9bee106c-511a-438c-ba8a-1087e0e2d199" alt=""><figcaption></figcaption></figure>

* After you create the workspace, go to it to launch Getint.

<figure><img src="https://4106311246-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MR6Z9V8zLATPQPOGSDf%2Fuploads%2FSwlBcYwrKjLLD7HSgfNe%2FLaunching%20the%20Getint%20app%20from%20app.getint.io%20(1).png?alt=media&amp;token=2b4549c2-ca54-4caa-a7e9-d6003f7984b1" alt=""><figcaption></figcaption></figure>

### 2. Create an Integration

* Go to **Workflows** (lightning bolt icon) and click **Create Integration**. From this menu, select **Continuous Sync** or **Data Migration**.

<figure><img src="https://4106311246-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MR6Z9V8zLATPQPOGSDf%2Fuploads%2FyOjqPGgLcj60ITpJ4RM5%2FContinuous%20Sync%20-%20Migration%20-%20Git%20Integration%20Sync.png?alt=media&amp;token=1473a035-6fba-4252-8c5f-e9de1b2cde86" alt=""><figcaption></figcaption></figure>

### 3. Connect to ClickUp

Any ClickUp user, including team members and guests, can generate a personal API token. Follow the steps below to generate one:

* Log in to your ClickUp account and click on your profile picture.
* Select **Settings**, then click on **ClickUp API** in the left-hand menu.
* Generate your access token, then copy and store it in a safe location.

{% embed url="<https://www.loom.com/share/af3b269f766041cf9ec0cd506799482a>" %}

* In Getint, click on **Connect App** and choose ClickUp, then select **Create a new connection**. Provide a name for the connection, paste your token in the **API TOKEN** field, and click **Add**.
* Once the connection is established, select the ClickUp Space and Folder you want to synchronize from the dropdown menu and click **Connect**.

{% hint style="warning" %}
ClickUp connections are set at the Folder level. You cannot select an individual List, so all Lists inside the selected Folder are synchronized.
{% endhint %}

### 4. Connect to Wrike

To connect Wrike, you need a Permanent Access Token. Follow the steps below to generate one:

* Log in to your Wrike account.
* Click on your initials on the top right of the page, select **Apps & Integrations**, then go to **API**.
* On the API tab, add a name for your token in the **App Name** field and click **Create New**.
* Scroll down to the bottom of the page and, under **Permanent Access Token**, select **Create Token**.
* Enter your Wrike password, click **Obtain token**, and then select **Copy Token**.

{% embed url="<https://youtu.be/HgyRhch-rgM>" %}

* In Getint, click on **Connect App** and choose Wrike, then select **Create a new connection**. Provide a name for the connection, paste the Permanent Access Token, and click **Add**.
* Once the connection is established, select the Wrike Space and Folder you want to synchronize from the dropdown menu and click **Connect**.

### 5. Configure Type Mapping

* **Quick Build**: Automatically map fields and types between applications with this feature.
* **Manual Mapping**: Use this feature for full control over the integration. Select **+ Add Type Mapping** and map ClickUp *Tasks* to Wrike *Tasks*.

{% hint style="info" %}
Tasks are the only item type supported for this integration. ClickUp sub-items and Wrike subtasks are not synchronized.
{% endhint %}

### 6. Item Routing

If you selected multiple Folders on one side, you must define Item Routing. All relevant information about defining conditions is here: [Syncing Many Projects](https://docs.getint.io/getintio-platform/syncing-many-to-many-projects#defining-conditions-in-items-routing).

### 7. Field Mapping

* Review or manually map fields within mapped types, including **title**, **description**, and **assignees**.
* Define the synchronization flow for each field, using the arrows in the middle and selecting **Apply**.

{% hint style="warning" %}
**Inline images** aren't supported for the **Description** field.
{% endhint %}

### 8. Assignee Mapping

* Use the assignee mapping option to match ClickUp assignees to Wrike assignees. For more details, visit our doc: [Assignees (users) mapping](https://docs.getint.io/getintio-platform/workflows/assignees-users-mapping).

### 9. Status Mapping

Wrike statuses are not retrieved automatically, so you need to add them manually by their status ID:

* In Getint, go to the **Status Mapping** tab.
* On the Wrike side, select **Add Option Manually**.
* Copy the Wrike status ID and paste it into Getint.
* Assign a name to the status and map it to its ClickUp counterpart. For example, ClickUp *Complete* could be mapped to Wrike *Completed*, and ClickUp *In Progress* to Wrike *In Progress*.
* Repeat for all statuses and then click **Apply**.

{% hint style="info" %}
**Tip:** Add and map statuses one at a time to avoid resetting the dropdown menu.
{% endhint %}

* You can also configure the status direction to support unidirectional transitions instead of bidirectional updates.

### 10. How to Manage Comments & Attachments

* Comments are enabled by default. You can configure these settings to match your organization's needs, such as selecting unidirectional or bidirectional sync and filtering by criteria like creation date or author.
* To synchronize attachments, toggle on the **Synchronize attachments** setting and choose the sync direction.

### 11. Advanced Tab

* Enable **Customize create/update actions** to manage item synchronization. This allows for specific rules, such as one-way creation for the left application combined with bidirectional updates.

### 12. Filtering

It is possible to filter the synchronization to fit your needs and requirements. Please see the doc [Items Filtering](https://docs.getint.io/getintio-platform/workflows/items-filtering) for more details.

**UI Filtering Option:**

* Click on the filtering icon near the app icon in your integration. This will apply to that side of the integration.
* Select if the filtering applies to *All*, *New*, and *Synced* items.
* Note that if the option **New items** is selected, the filtering will apply only to the new items, and the already synced items will continue to sync and update. If the option **Synced items** is selected, only the already synced items will be updated based on that filter.
* Choose the options and add the value for the filter. It is possible to filter more than one option for each field.
* Select **Apply** after creating the filters and **Save** the integration.

### 13. Test the Integration

* Create test tasks in ClickUp or Wrike and observe how they synchronize.
* Confirm that the data between the two platforms is correctly synced.
* Monitor the integration status and the logs in Getint to verify that everything functions as expected.

## Limitations and Considerations

At Getint, we continuously update our supported features, fields, and compatible apps. However, there are a few important points to consider for this integration:

* **Change History**: Getint cannot integrate the history of changes.
* **Comments**: Comments added by Getint will appear under the user account you choose during connection setup. The original author's name will appear in the comment footer, but the comment will be assigned to the connecting account.
* **Custom Fields**: Only specific custom field types can be mapped. ClickUp supports Dropdown, Labels, Number, People, and Text, and Wrike supports Date, Number, Single Select, and Text. Other custom field types are not available for mapping.
* **Dates**: Wrike Start Date and Due Date have no supported ClickUp field to map to.
* **Item Types**: ClickUp tasks and Wrike tasks are the only supported item types.
* **Multi-project Support**: Many-to-many project synchronization between ClickUp and Wrike is not supported.
* **Read-only Fields**: ClickUp Id, Item Type, Tags, and URL, and Wrike Id, Is Milestone, and URL can only be synced one way.
* **Statuses**: Wrike statuses must be added manually by status ID during Status Mapping.
* **Subtasks**: Syncing subtasks is not supported. ClickUp sub-items and Wrike subtasks are not synchronized.
* **Synchronization Scope**: In ClickUp, you can specify a Space and Folder, but not an individual List, which means all Lists in a Folder are synced.
* **Text Formatting**: Formatting is not fully preserved during synchronization. Bullet points may not convert correctly, and embedded links can be removed.

## ClickUp Wrike Licensing Model

The Getint licensing model for ClickUp and Wrike focuses on predictable costs and scalability:

### Standard Licensing

* This tier covers a direct integration between one ClickUp workspace and one Wrike account for a fixed fee. It includes unlimited project and task synchronization without hidden charges.

You can find more information about our pricing structure here: [Getint Pricing](https://www.getint.io/pricing).

### Network License

* Designed for managed service providers or large organizations, this option supports three or more instances. It allows for a specific number of connections (e.g., up to 10 instances) and provides the flexibility to swap integrated tools while the license is active.

For more details on licensing, visit our [Licensing Page](https://docs.getint.io/billing-and-services/licensing).

## Conclusion

Following this guide lets you set up the ClickUp Wrike integration with Getint. This configuration keeps tasks, statuses, comments, and attachments synchronized between both tools, so each team can keep working in the platform it already uses.

For further assistance, please contact us at the [Support Center](https://getint.io/help-center) or [Schedule a Demo](https://calendly.com/d/cpws-jb2-8xx/demo-call-all-team).

<figure><img src="https://4106311246-files.gitbook.io/~/files/v0/b/gitbook-x-prod.appspot.com/o/spaces%2F-MR6Z9V8zLATPQPOGSDf%2Fuploads%2F9OSEDBl869gRue9mQAwv%2FGetint%20Yellow%20Banner.png?alt=media&amp;token=9cc42142-6e48-4931-8fd5-cbf7dcf4cdc1" alt=""><figcaption><p><a href="https://calendly.com/d/cpws-jb2-8xx/demo-call-all-team">Start your integration journey. Schedule a free consultation with our Getint Integration Expert today!</a></p></figcaption></figure>
