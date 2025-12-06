
## Implement login, subscription support

Permissions are implemented based on the page/ui action the user is allowed to perform. Backend may send extraneous data, but it's up to frontend to use permissions truncate what the user will see

### Login checks
1. Check if the there is auth data for these crendentials
2. Check if this is an internal or external user
    1. if internal, check if the user is locked or not
        1. If locked, force logout and show an error toast
        2. If not locked, check if the user has a role
            1. If no role, abort all backend async request and display a banner to replace all unauthorized components/page
            2. If role, check the permissions for the role
                1. If no permissions, abort all backend async request and display a banner to replace all unauthorized components/page
                2. If permissions, give access to the requested page
                    1. Check if the permission gives user access to use the given page, component or action
                        1. If no access, abort all backend async request and display a banner to replace all unauthorized components/page
                        2. If access, give access to the requested page/component/action
    2. if external, check if the user's company has a subscription
        1. If no subscription or subscription is expired, redirect to billing page
        2. If subscription is inactive, force logout and show an error toast
        3. If subscription is active, check if the user is locked or not
            1. If locked, force logout and show an error toast
            2. If not locked, proceed to step 3
            3. Check if the user has completed onboarding
                1. If not completed, redirect to onboarding page
                2. If completed, proceed to permissions checking
                3. Check if the user has permissions to access the requested page
                    1. If no permissions, abort all backend async request and display a banner to replace all unauthorized components/page
                    2. If permissions, check if the user has a role
                        1. If no role, abort all backend async request and display a banner to replace all unauthorized components/page
                        2. If role, check the permissions for the role
                            1. If no permissions, abort all backend async request and display a banner to replace all unauthorized components/page
                            2. If permissions, give access to the requested page

## Fix the following:
- Prevent role deactivation if the current user is assigned to that role
- Create a `VerandaView` or `ThresholdView` for every page that requires authentication. This is where the super admins will be distinguished from regular users and where the permissions will be checked before rendering the actual page component.
- Optimize the platform by preventing unnecessary backend calls for data that is already available in the store. This means using stores (pinia) to cache states and response payloads instead of reloading the page component which triggers the `onMounted` lifecycle hook and subsequent backend calls to fetch data that is already in the store.
- Replace the circular progress bar on the dashboard with a linear progress bar
- Permissions are broken
- Add SEOs metadata to all pages
- Update the env for cloudflare deployment
- Send the token with the request data for initial user signup
- Add a logic to link a company with it's parent `managedBy`
- Implemnts bulk roles
